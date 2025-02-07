This shows how we can compare two kustomize deployments to see if they are the same or not.

```bash
> diff <(kustomize build deployment1) <(kustomize build deployment2); [ $? -eq 0 ] && echo "No differences" || echo "Differences found or error"
> Success
```

If you are using this repo as a playground to compare deployments, you can run the following helper command as a shortcut.
```bash
./kompare deployment1 deployment2
```

Bonus: Add this to your `.bashrc` or `.bash_profile` or `.zshrc` to make it easier to compare two deployments.
```bash
kompare () {
  diff <(kustomize build $1) <(kustomize build $2)
  if [ $? -eq 0 ]; then
    echo "No differences"
  else
    echo "Differences found or error"
  fi
}
```
