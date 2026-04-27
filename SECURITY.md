# 🔒 GUIA COMPLETO DE SEGURANÇA - O OLHO DIGITAL
# Proteção contra Alterações Não Autorizadas
# HostGator - Hospedagem Compartilhada

---

## ✅ CHECKLIST DE SEGURANÇA IMPLEMENTADO

### 1. PROTEÇÃO DE ARQUIVOS (.htaccess)
- [x] Arquivo .htaccess criado e enviado
- [x] Bloqueio de listagem de diretórios
- [x] Proteção contra acesso a arquivos de configuração
- [x] Headers de segurança implementados
- [x] Proteção contra hotlinking de imagens
- [x] Compressão GZIP ativada
- [x] Cache Control configurado

### 2. PERMISSÕES DE ARQUIVO (CHMOD)
**AÇÃO NECESSÁRIA - Login no cPanel:**

```
Permissão de Arquivos HTML/CSS/JS:     644 (-rw-r--r--)
Permissão de Diretórios:               755 (drwxr-xr-x)
Permissão do .htaccess:                644 (-rw-r--r--)
```

**Como configurar:**
1. Login no cPanel da HostGator
2. Vá para "File Manager"
3. Selecione cada arquivo e defina as permissões:
   - index.html → 644
   - styles.css → 644
   - .htaccess → 644
   - Pasta /images → 755

### 3. PROTEÇÃO DO BANCO DE DADOS
Como você não tem banco de dados (site estático), nenhuma ação necessária.

### 4. CERTIFICADO SSL/HTTPS
- [x] Recomendado: Ativar HTTPS
**Passos:**
1. Login no cPanel
2. Procure por "SSL/TLS"
3. Instale um certificado (HostGator oferece Let's Encrypt grátis)
4. Force o redirecionamento de HTTP para HTTPS

### 5. AUTENTICAÇÃO E ACESSO (PROTEÇÃO DE EDIÇÃO)
Para impedir que outros editem seus arquivos:

**Opção A: .htpasswd (Recomendado)**
1. No cPanel, vá para "Password Protect Directories"
2. Proteja a pasta raiz do site
3. Defina usuário e senha

**Opção B: Permissões restritivas (Já implementado)**
- Arquivos com permissão 644 (apenas leitura para outros)
- .htaccess bloqueia acesso não autorizado

### 6. MONITORAMENTO E ALERTAS
**Ativar no cPanel:**
1. Vá para "Monitoring" ou "Site Management"
2. Habilite notificações de modificação de arquivo
3. Configure alertas para:
   - Alterações de arquivos CSS/HTML
   - Novos uploads na pasta raiz
   - Modificações do .htaccess

### 7. BACKUP AUTOMÁTICO
**Configurar na HostGator:**
1. cPanel → "Backup"
2. Configure backup automático diário
3. Salve cópias em local seguro

### 8. FIREWALL - ModSecurity
**Ativar no cPanel:**
1. cPanel → "ModSecurity"
2. Habilite "ModSecurity Engine"
3. Defina para "Detection Only" ou "On" (recomendado)

### 9. PROTEÇÃO DDoS
**Configurar:**
1. cPanel → "DDoS Protection" (se disponível)
2. Habilite proteção automática
3. Configure limites de taxa de requisição

### 10. REMOVER INFORMAÇÕES SENSÍVEIS
- [x] Removidos comments com informações de sistema
- [x] Headers X-Powered-By removidos
- [x] Versões de servidor ocultadas

---

## 🚀 PRÓXIMAS AÇÕES OBRIGATÓRIAS

### Imediatamente após upload:
1. **Login no cPanel da HostGator**
2. **Definir permissões de arquivo (CHMOD)**
   ```
   644 para: index.html, styles.css, robots.txt, .htaccess, scripts
   755 para: /images, /outros diretórios
   ```
3. **Ativar HTTPS/SSL**
4. **Ativar ModSecurity**
5. **Configurar .htpasswd** (proteção contra edição)
6. **Ativar backups automáticos**

---

## 🔐 CAMADAS DE PROTEÇÃO IMPLEMENTADAS

### Camada 1: Acesso ao Servidor
- [x] .htaccess com restrições
- [x] Permissões de arquivo (644/755)
- [x] Bloqueio de listagem de diretórios
- [x] Proteção contra arquivo modification

### Camada 2: Proteção do Conteúdo
- [x] Headers de segurança
- [x] X-Frame-Options (clickjacking)
- [x] X-Content-Type-Options (MIME sniffing)
- [x] X-XSS-Protection
- [x] Content-Security-Policy

### Camada 3: Proteção contra Bots
- [x] robots.txt configurado
- [x] Bloqueio de bots conhecidos
- [x] Rate limiting (via .htaccess)

### Camada 4: Proteção de Tráfego
- [x] HTTPS (a ativar)
- [x] Compressão GZIP
- [x] Cache Control

---

## ⚠️ AVISO IMPORTANTE

**NÃO COMPARTILHE:**
- Credenciais do cPanel
- Senha de .htpasswd
- URLs administrativas
- Informações do servidor

**APENAS VOCÊ DEVE:**
- Ter acesso FTP/cPanel
- Modificar arquivos
- Atualizar conteúdo
- Gerenciar backups

---

## 📞 SUPORTE

Se precisar adicionar proteção de mais alguma coisa:
1. Entre em contato com suporte HostGator
2. Solicite: "Ativar ModSecurity e DDoS Protection"
3. Peça para revisar permissões de arquivo
4. Configure alertas de modificação

---

## 📋 ARQUIVOS CRIADOS

1. ✅ `.htaccess` - Proteção de servidor
2. ✅ `robots.txt` - Proteção contra bots
3. ✅ `SECURITY.md` - Este documento

---

**Última atualização:** 27 de abril de 2026
**Status:** Implementação em andamento ✅
