
## How to change the location of the default installation package for julia

For the Julia packages there is one system variable that controls everything.
It is named `JULIA_DEPOT_PATH`.

In case of Windows you could set it to something like the following in
[[code.power-shell]]:

```powershell
$env:JULIA_DEPOT_PATH = "C:\path\to\my_julia_depo_folder"
```

### Source

* <https://stackoverflow.com/questions/76072461/how-to-change-the-location-of-the-default-installation-package-for-julia-1-8-5>
