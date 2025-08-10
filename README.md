# Projeto: Servidor de ISOs Linux com Docker

Este projeto tem como objetivo criar um servidor local para distribuição de arquivos ISO de sistemas Linux,
utilizando Docker e Nginx para disponibilizar os arquivos via navegador.

---

## 👩‍💻 Responsável
**Terinela Agostinho**  
Tarefa: Upload e organização das distribuições Linux.

---

## 📁 Estrutura de Pastas

```
linux-iso-server/
├── isos/
│   ├── ubuntu/
│   │   └── ubuntu-22.04.4-desktop-amd64.iso
│   ├── debian/
│   │   └── debian-12.5.0-amd64-netinst.iso
│   └── fedora/
│       └── Fedora-Workstation-Live-x86_64-40-1.14.iso
├── index.html
├── Dockerfile
├── docker-compose.yml
└── README.md
```

---

## 📊 Diagrama da Arquitetura

![Arquitetura do Servidor de ISOs](arquitetura_iso_server.png)

---

## 📦 Etapas Realizadas

1. **Criação da estrutura de pastas** para armazenar as ISOs por distribuição.
2. **Download** das distribuições Ubuntu, Debian e Fedora em suas respectivas pastas.
3. **Correção de permissões** para garantir acesso de leitura aos arquivos.
4. **Criação de uma página HTML** (`index.html`) com links diretos para cada ISO.
5. **Configuração do Nginx** via Docker e Docker Compose.
6. **Testes de acesso** pelo navegador usando o IP da máquina virtual.

---

## 🌍 Acesso ao Servidor

Servidor disponível localmente em:

```
http://10.0.2.15:8080
```

Links diretos para as ISOs:
- [Ubuntu 22.04.4](http://10.0.2.15:8080/isos/ubuntu/ubuntu-22.04.4-desktop-amd64.iso)
- [Debian 12.5.0](http://10.0.2.15:8080/isos/debian/debian-12.5.0-amd64-netinst.iso)
- [Fedora 40](http://10.0.2.15:8080/isos/fedora/Fedora-Workstation-Live-x86_64-40-1.14.iso)

---

## 🚀 Como Executar

### **Iniciar o servidor**
Dentro da pasta `linux-iso-server`:

```bash
docker-compose up -d
```

### **Parar o servidor**
```bash
docker-compose down
```

### **Reiniciar o servidor**
```bash
docker-compose down
docker-compose up -d
```

### **Atualizar a imagem Docker**
Se precisar atualizar a imagem do Nginx ou rebuildar:
```bash
docker-compose down
docker-compose build --no-cache
docker-compose up -d
```

---

## ✅ Conclusão

Todas as distribuições foram organizadas e disponibilizadas com sucesso via servidor web.
A solução é simples de gerenciar e pode ser facilmente expandida para outras ISOs.