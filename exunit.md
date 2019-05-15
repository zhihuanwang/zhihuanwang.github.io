---
title: ExUnit
category: Elixir
layout: 2017/sheet
updated: 2017-08-26
---

### Test cases

```elixir
defmodule MyTest do
  use ExUnit.Case
  use ExUnit.Case, async: true  # for async

  test "the truth" do
    assert 1 + 1 == 2
  end
end
```

### Capture IO

```elixir
import ExUnit.CaptureIO

test "capture io" do
  result = capture_io(fn ->
    IO.puts "sup"
  end)

  assert result == "sup\n"
end
```

### Capture logs

```elixir
config :ex_unit, capture_logs: true
```

### Async

```elixir
defmodule AssertionTest do
  # run concurrently with other test cases
  use ExUnit.Case, async: true
end
```

### Assertions

```elixir
assert x == y
refute x == y

assert_raise ArithmeticError, fn ->
  1 + "test"
end

assert_raise ArithmeticError, "message", fn -> ...
assert_raise ArithmeticError, ~r/message/, fn -> ...

flunk "This should've been an error"
```

See: [Assertions](http://devdocs.io/elixir/ex_unit/exunit.assertions)

## Also see
{: .-one-column}

- <http://devdocs.io/elixir/ex_unit/exunit#configure/1>
