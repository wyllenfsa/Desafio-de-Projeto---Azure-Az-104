# Desafio de Projeto Azure Az-104
Dicas e resumos dos principais recursos da Azure com foco em auxiliar na preparação para a certificação Microsoft - Azure Administrator Certification (AZ-104)

## ✅ Administração de Identidade – MS Entra ID

### Visão Geral:
O **MS Entra ID** é a solução de Gerenciamento de Identidade e Acesso (IAM) da Microsoft em nuvem. Ele é essencial para autenticação, autorização e governança de usuários e aplicativos.

### Principais Recursos:
- Usuários e Grupos
- Azure AD Connect: Sincronização de identidades locais com a nuvem.
- Autenticação Multifator (MFA)
- Acesso Condicional
- Identidades Gerenciadas para Recursos do Azure (Managed Identities)
- Enterprise Applications / Single Sign-On (SSO)
- Privileged Identity Management (PIM): Controle de acesso privilegiado.

### Dicas de Configuração:
- Habilitar MFA para todas as contas administrativas.
- Usar Grupos Dinâmicos para automação.
- Criar políticas de acesso condicional para proteger apps sensíveis.
- Monitorar sign-in logs e audit logs regularmente.

---

## ✅ Administração de Governança e Conformidade

### Assinaturas do Azure:
- Cada Subscription isola recursos por finalidade (ex: Produção, Dev, Teste).
- Cada assinatura tem limites de recurso, políticas próprias e controle de custos.
- Integração com Azure Cost Management.

### Azure Policy:
- Garante governança automática sobre os recursos.
- Exemplo de políticas:
  - Bloquear criação de VMs em regiões não permitidas.
  - Exigir uso de tags obrigatórias.
  - Aplicar configuração obrigatória de SKU de VMs.

### Iniciativas (Policy Initiative):
- Agrupamento de múltiplas políticas para facilitar aplicação em larga escala.

### RBAC (Role-Based Access Control):
- Permissões granulares e específicas por recurso.
- Principais roles:
  - Owner: Controle total.
  - Contributor: Pode criar/modificar recursos.
  - Reader: Apenas leitura.
- Custom Roles: Permite criar roles com permissões específicas.

---

## ✅ Administração dos Recursos do Azure

### Ferramentas de Gerenciamento:
- Portal Azure: GUI.
- Azure CLI: Linha de comando (multiplataforma).
- PowerShell for Azure: Scripting avançado.
- REST API / SDKs: Automação personalizada.
- ARM Templates: Infraestrutura como código (IaC).

### Modelos ARM (Azure Resource Manager):
- Deploy declarativo.
- Suporte a modularização, parâmetros, condições.
- Alternativas:
  - Bicep: Linguagem mais simples para templates ARM.
  - Terraform: IaC multi-cloud.

---

## ✅ Administração de Rede Virtual

### Redes Virtuais (VNet):
- Equivalente a uma rede local em nuvem.
- Suporte a sub-redes, endereço IP privado, peering, VPN.

### Grupos de Segurança de Rede (NSG):
- Controle de tráfego por porta, protocolo, endereço IP.
- Aplicável a sub-redes ou NICs de VMs.

### Application Security Groups (ASG):
- Permite agrupar VMs por função lógica ao invés de IP.
- Exemplo: Criar um ASG chamado WebServers e aplicar regras de NSG baseadas nele.

### DNS do Azure:
- Public DNS Zones: Para sites públicos.
- Private DNS Zones: Para resolução de nomes internos.
- Custom DNS: Configurável por VNet.

### Dicas:
- Use ASGs para simplificar regras em ambientes com múltiplas VMs.
- Sempre combine NSGs e ASGs para reforço de segurança.

---

## ✅ Administração de Conectividade entre Sites

### VNet Peering:
- Comunicação privada entre VNets.
- Opções:
  - Intra-regional: Mesma região.
  - Global Peering: Entre diferentes regiões.

### Private Endpoints:
- Permite acesso privado a serviços como Storage Account, SQL, App Services.
- Usa IP privado da VNet.

### User Defined Routes (UDR):
- Personalização de roteamento interno.
- Exemplo: Forçar tráfego para uma appliance de segurança.

---

## ✅ Administração do Tráfego de Rede

### Azure Load Balancer:
- Balanceador de tráfego Layer 4 (TCP/UDP).
- Modelos: Interno e Público.

### Gateway de Aplicativo (App Gateway):
- Layer 7 com recursos avançados:
  - Roteamento baseado em URL
  - Web Application Firewall (WAF)
  - SSL Offload

### Network Watcher:
- Diagnóstico de conectividade.
- Ferramentas úteis:
  - NSG Flow Logs
  - Connection Troubleshoot
  - Packet Capture

---

## ✅ Administração do Armazenamento do Azure

### Tipos de Conta de Armazenamento:
- General Purpose v2 (GPv2)
- BlobStorage: Foco em blobs.

### Replicação de Dados:

| Tipo      | Característica                          |
|-----------|-----------------------------------------|
| LRS       | Cópia local                             |
| ZRS       | Cópia em 3 zonas na mesma região        |
| GRS       | Cópia geográfica em região secundária   |
| RA-GRS    | GRS com leitura disponível              |
| GZRS      | Zonal + geográfica                      |
| RA-GZRS   | GZRS com leitura na região secundária   |

### Armazenamento de Blobs:
- Tipos: Block Blob, Append Blob, Page Blob.
- Tier de acesso: Hot, Cool, Archive.

### Segurança:
- Access Keys
- Shared Access Signatures (SAS)
- Private Endpoints
- RBAC e Azure AD

### Azure Files:
- Compartilhamento de arquivos via SMB.
- Suporte a AD DS para autenticação.

---

## ✅ Administração de Máquinas Virtuais do Azure

### Tipos de VM:
- General Purpose, Compute Optimized, Memory Optimized, GPU.

### Opções de Disponibilidade:
- Availability Sets: Alta disponibilidade em nível de rack.
- Availability Zones: Alta disponibilidade em nível de datacenter.
- Scale Sets: Escalabilidade automática horizontal.

### Dicas:
- Habilitar Disk Encryption.
- Fazer uso de Snapshot para backups rápidos.

---

## ✅ Administração de Opções de Computação PaaS

### App Service Plans:
- Define quantidade de recursos alocados ao App Service.
- Níveis: Free, Shared, Basic, Standard, Premium, Isolated.

### App Services:
- Hospedagem de sites, APIs, backends.
- Suporte a deployment slots e integração com GitHub.

### Azure Container Instances (ACI):
- Execução rápida e isolada de containers.
- Pagamento por segundo.

---

## ✅ Administração de Proteção de Dados

### Backup de Arquivos e Pastas:
- Azure Backup Agent
- Integração com Recovery Services Vault.

### Backup de VMs:
- Backup completo com ponto de restauração.
- Opção de restore de arquivos individuais.
- Backup incremental.

---

## ✅ Administração de Monitoramento

### Azure Monitor:
- Coleta e análise de métricas.

### Azure Alerts:
- Alertas baseados em:
  - Métricas
  - Logs
  - Atividades (Activity Logs)

### Log Analytics:
- Análise centralizada de logs com KQL (Kusto Query Language).

### Dicas:
- Use Workbooks para dashboards personalizados.
- Habilite Diagnostic Settings para serviços críticos.

---
