# beaker-run-action

## Inputs

### `spec`

A JSON-serialized experiment spec.

### `token`

Your Beaker token.

### `workspace`

The Beaker workspace to use.

### `clusters`

A comma-separated list of clusters that can be used to override the cluster
in the spec for a task if any of them have enough resources avaiable.

## Example

```yaml
uses: allenai/beaker-run-action@v1
with:
  spec: |
    {"version": "v2-alpha", "description": "Hello, World!", "tasks": [{"name": "hello", "image": {"docker": "hello-world"}, "context": {"cluster": "ai2/petew-cpu"}, "result": {"path": "/unused"}}]}
  token: ${{ secrets.BEAKER_TOKEN }}
  workspace: ai2/petew-testing
  clusters: ai2/general-cirrascale,ai2/allennlp-cirrascale
```
