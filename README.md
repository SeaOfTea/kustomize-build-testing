This shows how we can compare two kustomize deployments to see if they are the same or not.

```bash
> diff <(kustomize build deployment1) <(kustomize build deployment2); if [ $? -eq 0 ]; then echo "Success"; else echo "Failure"; fi
> Success
```
