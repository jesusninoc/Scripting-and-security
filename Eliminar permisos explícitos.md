# Eliminar permisos explícitos
## Filesystem, Permissions, PowerShell 
### URL: https://www.jesusninoc.com/2016/03/30/eliminar-permisos-explicitos/
```PowerShell
#Los permisos explícitos son aquellos que se establecen de forma predeterminada en objetos que no son secundarios cuando se crea el objeto, o los que crea el usuario en objetos secundarios, primarios o que no son secundarios.

$Path = ‘F:\power\permisos’
$acl = Get-Acl -Path $path
$acl.Access | Select-Object IdentityReference,IsInherited

#Eliminar permisos explícitos
#RemoveAccessRule quita todos permisos de la lista de control de acceso (ACL) Allow o Deny coincidentes del archivo o directorio actual.
$acl.Access | Where-Object{!($_.isInherited)} | ForEach-Object {$acl.RemoveAccessRule($_)}
$acl.Access | Select-Object IdentityReference,IsInherited

#Asignar nuevos permisos
$acl | Set-Acl -Path $path

```
