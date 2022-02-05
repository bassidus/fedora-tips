## Improve dnf config with parallel downloads and more

Edit ```/etc/dnf/dnf.conf``` and add following lines:
```
[main]
gpgcheck=1
installonly_limit=3
clean_requirements_on_remove=True
best=False
skip_if_unavailable=True
fastestmirror=1
max_parallel_downloads=10
deltarpm=true
defaultyes=true
```
