# assert

An __experimental__ generic test assertion library in Go. Serious projects should use something else, I just wanted to experiment with idiomatic, type-safe generic assertions.

## examples

```go
import "github.com/nate-anderson/asssert"

func TestFoo(t *testing.T) {
    // comparable values
    assert.That(t, actual).Equals(exp)

    // errors
    assert.ThatError(t, err).IsNil()
    assert.ThatError(t, err).Is(someParentError)

    // strings
    assert.ThatString(t, actual).Contains("something_shorter")

    // maps
    assert.ThatMap(t, someMap).ContainsKey("key")
    assert.ThatMap(t, someMap).HasValueAt("key", "my_value")
    assert.ThatMap(t, someMap).HasLength(1)
    
    // slices
    assert.ThatSlice(t, someSlice).ContainsAll(expValues)
    assert.ThatSlice(t, someSlice).Equals(expValues)
    assert.ThatSlice(t, someSlice).HasLength(3)
}
```