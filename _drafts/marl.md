---
layout: post
title: "marl, hypothesis"
---

## Are new users the problem with software?

This article asks the question "why do applications seem _worse_ than they used to?". The author argues that since user-base growth is a common metric for the success of an app, companies are incentivized only to keep drawing in new users rather than focusing on existing users. To draw in new users, they simplify the app, generally creating a worse experience for existing users. The author points to websites like Reddit and Craigslist for counter-examples. Neither has changed (meaningfully) in years yet enjoy continuing popularity.

Article: <https://nothinghuman.substack.com/p/the-tyranny-of-the-marginal-user>

## hypothesis

hypothesis is a python library to help with testing. The idea is that you want to test a function which has some arguments. You can use hypothesis to automatically run a bunch of random and likely offending values through the function and see if it breaks. For a real world example, I wrote a simple angle normalization function recently:

```python
def normalize_angle(angle: float) -> float:
    """Normalize angle to range [0, 2*pi)"""
    return (angle + 2 * pi) % (2 * pi)
```

which looked pretty solid. I slapped some normal unit tests on it with some values I dreamed up (-pi -> pi, 2pi -> 0, 3pi -> pi, etc) and the tests passed. But I then added hypothesis like so:

```python
from hypothesis import given, strategies as st

@given(angle=st.floats())
def test_normalize_any_angle(angle: float) -> None:
    assert 0.0 <= normalize_angle(angle) < 2.0 * pi
```

which failed with the following error:

```bash
    @given(angle=st.floats())
    def test_normalize_any_angle(angle: float) -> None:
>       assert 0.0 <= normalize_angle(angle) < 2.0 * pi
E       assert 0.0 <= nan
E        +  where nan = normalize_angle(inf)
E       Falsifying example: test_normalize_any_angle(
E           angle=inf,
E       )
```

Right, `inf` is a float, and one of the default values in the `st.floats()` "test strategy". I needed to add a catch for nans/infs/etc. In some cases this type of testing may be overkill but the principle at play is: "You said your function would take any float. Does it?". I particularly like to use it when the tests I've written are trivial examples I've dreamed up (-pi -> pi, ...). It's preferable in these cases to have hypothesis pressure test your functions.
