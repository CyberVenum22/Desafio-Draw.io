# Desafio-Draw.io
# ☁️ Lab AWS: Gerenciamento de EC2, AMIs e Snapshots
## 🗺️ Arquitetura do Lab

Montei esse diagrama no Draw.io para ilustrar o fluxo de ponta a ponta do que foi feito no laboratório:

### Entendendo o fluxo:
1. **O Início:** O usuário (`Actor`) envia arquivos do seu computador para o **Volume EBS Original**, que está atrelado à nossa instância **EC2** base. Essa máquina também se conecta a um banco de dados **RDS**.
2. **Segurança (Snapshot):** Criamos um **EBS Snapshot** direto do volume original. Ele funciona como um backup incremental dos arquivos (salva só o que mudou, economizando custos).
3. **Escalabilidade (AMI):** Geramos uma **Custom AMI** (um "molde" ou template do servidor). 
4. **O Clone:** Usando essa AMI, conseguimos subir uma nova máquina idêntica num piscar de olhos, resultando no **Volume EBS Clonado** com tudo pronto e configurado.

---

## 💡 Principais Aprendizados

> 📌 **A grande virada de chave:** Entender a diferença prática entre os dois backups. O **Snapshot** guarda os *dados do disco* (arquivos). A **AMI** guarda a *alma da máquina* (sistema operacional, configurações e programas instalados), permitindo clonar o servidor para aguentar mais acessos ou recuperar o ambiente em segundos se algo der errado.

- **Gerenciamento de Custos:** Lembrar sempre de encerrar os recursos e deletar os snapshots/AMIs antigos para não gerar cobranças desnecessárias na conta AWS.

---
