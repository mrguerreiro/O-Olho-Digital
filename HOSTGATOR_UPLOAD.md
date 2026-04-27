# 📤 INSTRUÇÕES DE UPLOAD PARA HOSTGATOR

## ARQUIVOS A ENVIAR

1. **index.html** - Página principal
2. **styles.css** - Estilos
3. **.htaccess** - ⭐ CRÍTICO - Proteção de segurança
4. **robots.txt** - Proteção contra bots
5. **Pasta /images** - Todas as imagens

---

## PASSO A PASSO DE UPLOAD

### OPÇÃO 1: Usando File Manager do cPanel (Mais Fácil)

1. **Login no cPanel**
   - Acesse: https://seu-dominio.com:2083
   - User: seu_usuario
   - Senha: sua_senha

2. **Abra File Manager**
   - Procure por "File Manager" no cPanel
   - Clique em "public_html"

3. **Faça Upload dos Arquivos**
   - Clique em "Upload"
   - Selecione: index.html, styles.css, .htaccess, robots.txt
   - Clique em "Upload Files"

4. **Faça Upload da Pasta /images**
   - Clique em "+ Folder"
   - Nome: "images"
   - Clique em "Create"
   - Entra na pasta e faça upload de todas as imagens

5. **Defina as Permissões (CHMOD)**
   - Clique com botão direito em cada arquivo
   - "Permissions" → Defina como 644
   - Para a pasta /images → 755

6. **Ative HTTPS**
   - Procure "SSL/TLS" no cPanel
   - Ative certificado Let's Encrypt
   - Force HTTPS no seu site

---

### OPÇÃO 2: Usando FTP (Se souber usar)

**Com FileZilla ou outro cliente FTP:**

1. **Conecte ao servidor FTP**
   ```
   Host: seu-dominio.com
   User: seu_usuario_ftp
   Password: sua_senha_ftp
   Port: 21
   ```

2. **Navegue até /public_html**

3. **Faça upload dos arquivos:**
   - Clique direito → Upload Files
   - Selecione todos os arquivos

4. **Defina permissões:**
   - Clique direito em cada arquivo → File Permissions
   - Arquivos: 644
   - Pasta /images: 755

---

## CONFIGURAÇÕES APÓS UPLOAD NO cPANEL

### ✅ Passo 1: Ativar HTTPS/SSL
1. Acesse cPanel
2. Procure "SSL/TLS"
3. Clique em "Manage SSL sites"
4. Instale Let's Encrypt (grátis)
5. Force redirecionamento HTTP → HTTPS

### ✅ Passo 2: Ativar ModSecurity
1. Acesse cPanel
2. Procure "ModSecurity"
3. Clique em "ModSecurity Engine: ON"
4. Defina para "Processing mode"

### ✅ Passo 3: Configurar Backup Automático
1. Acesse cPanel
2. Procure "Backup Wizard"
3. Configure backup diário
4. Salve backups em local seguro

### ✅ Passo 4: Proteger Diretório com Senha (Opcional)
1. Acesse cPanel
2. Procure "Password Protect Directories"
3. Selecione a pasta do seu site
4. Defina usuário e senha
5. Isso impedirá acesso não autorizado

### ✅ Passo 5: Ativar DDoS Protection
1. Acesse cPanel
2. Procure "DDoS Protection"
3. Habilite "Imunify360" (se disponível)
4. Configure alertas

### ✅ Passo 6: Monitoramento
1. Acesse cPanel
2. Procure "File Manager"
3. Configure alertas para modificações de arquivo
4. Ative notificações por email

---

## APÓS FAZER UPLOAD - VERIFICAR

```bash
✓ Arquivo .htaccess está em /public_html
✓ Permissão do .htaccess é 644
✓ Arquivo robots.txt está em /public_html
✓ HTTPS está ativado (URL começa com https://)
✓ Imagens carregam corretamente
✓ Estilos CSS estão aplicados
✓ Nenhuma mensagem de erro no console
```

---

## TESTAR SEGURANÇA

Após upload, teste acessando:

1. **Página principal:**
   ```
   https://seu-dominio.com
   ```

2. **Tentar acessar .htaccess (deve falhar):**
   ```
   https://seu-dominio.com/.htaccess
   ```
   ✓ Esperado: Erro 403 Forbidden

3. **Listar diretórios (deve falhar):**
   ```
   https://seu-dominio.com/images/
   ```
   ✓ Esperado: Erro 403 Forbidden

4. **Verificar headers de segurança:**
   Abra DevTools (F12) → Network → Clique na página → Headers
   ✓ Deve conter: X-Frame-Options, X-Content-Type-Options, etc.

---

## CONTATO HOSTGATOR EM CASO DE DÚVIDAS

- **Chat 24/7:** https://www.hostgator.com/support
- **Ticket:** Crie um ticket no cPanel
- **Telefone:** +55 (consulte seu contrato)

Solicite especificamente:
- "Ativar ModSecurity"
- "Ativar DDoS Protection"
- "Confirmar SSL/HTTPS ativo"
- "Revisar permissões de arquivo"

---

**Atualizado:** 27 de abril de 2026
