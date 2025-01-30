## Reasons for Forking

### 1. Fixed Application Port Issue  
In the GSA POD, the application was expected to run on port 80 but was instead running on port 9392. This issue was observed in the logs:  
```
C:\workspace\projects\csx-group>kubectl logs openvas-67ffdd5bc4-pjbbx -n openvas -c gsa
starting gsad
gsad main-Message: 15:30:43.918: Starting GSAD version 24.1.1


(gsad:13): gsad main-WARNING **: 15:30:43.919: Binding to port 80 failed, trying default port 9392 next.
```
This fork includes a fix to ensure the application binds correctly to the intended port.

### 2. Enabled HostPath Volume  
Configured HostPath volume support to meet specific storage requirements.

### 3. Custom Ingress and SSL Configuration  
Added a custom Ingress setup along with custom SSL certificate configuration for secure access.
