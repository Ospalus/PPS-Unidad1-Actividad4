<p style="text-align: justify;">

## PPS-Unidad1-Actividad4
# 🛡️ Alternativas para Probar una Aplicación en una Caja de Arena (Sandbox)

## 🔹 1. Firejail (con Firetools) ✅  
**Descripción:**  
Firejail es una herramienta de sandboxing que utiliza **namespaces** y **seccomp** de Linux para aislar procesos. Son una función del kernel de Linux que permite aislar recursos del sistema, como procesos, red, sistema de archivos y usuarios. Esto permite que diferentes procesos operen en entornos separados sin interferir entre sí. Firetools es su interfaz gráfica.  

**Instalación:**  
```bash
sudo apt-install update
sudo apt install firejail firetools  # Debian/Ubuntu
```
**Ejemplo de uso:**  

```bash
firejail firefox
```

---

## 🔹 2. Bubblewrap  
**Descripción:**  
Bubblewrap es una herramienta ligera para aislar aplicaciones usando namespaces. Se usa en Flatpak.  

**Instalación:**  
```bash
sudo apt install bubblewrap  # Debian/Ubuntu
```
**Ejemplo de uso:**  
```bash
bwrap --ro-bind / / --dev /dev --proc /proc --unshare-net bash
```

---

## 🔹 3. AppArmor  
**Descripción:**  
AppArmor restringe las acciones de una aplicación mediante perfiles de control de acceso.  

**Ver si está activo:**  
```bash
aa-status
```
**Habilitar perfil para una aplicación:**  
```bash
sudo aa-enforce /etc/apparmor.d/usr.bin.firefox
```

---

## 🔹 4. SELinux  
**Descripción:**  
SELinux es una alternativa más avanzada a AppArmor, utilizada en Fedora y RHEL.  

**Ver estado:**  
```bash
sestatus
```

---

## 🔹 5. Docker  
**Descripción:**  
Docker permite ejecutar aplicaciones en contenedores, proporcionando aislamiento del sistema anfitrión.  

**Instalación:**  
```bash
sudo apt install docker.io  # Debian/Ubuntu
```
**Ejemplo de uso:**  
```bash
docker run --rm -it ubuntu bash
```

---
# 🔹 Conclusión
Las herramientas de sandboxing, como Firejail, Bubblewrap, AppArmor, SELinux y Docker, proporcionan diferentes niveles de aislamiento para ejecutar aplicaciones de forma segura. Firejail, en particular, destaca por su facilidad de uso y eficiencia al emplear namespaces y seccomp para restringir el acceso a recursos del sistema.

Cada herramienta tiene su propósito: Firejail y Bubblewrap son ideales para aislar aplicaciones individuales, AppArmor y SELinux refuerzan la seguridad mediante políticas de control de acceso, mientras que Docker es útil para ejecutar aplicaciones en entornos completamente encapsulados.

</p>

