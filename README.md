# Fission Action Demo 🚀

This repository demonstrates [Fission action](https://github.com/fission/action) with a simple NodeJS based function using Fission specs. The Fission action in the workflow applies the spec on a push event. The action needs three secrets and a simple workflow is defined as:

```
workflow "Fission CD" {
  on = "push"
  resolves = ["FissionCD"]
}

action "FissionCD" {
  uses = "docker://vishalbiyani/fission-action:7"
  secrets = ["CERTIFICATE_AUTHORITY", "SERVER_ADDRESS", "USER_TOKEN"]
}
```


## Testing Locally

You can test actions locally with [Act](https://github.com/nektos/act) but this action can not be tested due to [this issue](https://github.com/nektos/act/issues/53)