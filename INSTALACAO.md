# Instalar o Nimos

> **Antes de começar:** o Nimos ainda não tem os certificados de assinatura da Apple e da
> Microsoft. É uma decisão de cronograma, não um problema com o programa — mas significa
> que o sistema vai exibir um aviso na primeira abertura. Esta página mostra como passar
> por ele, e como conferir que o arquivo que você baixou é mesmo o nosso.
>
> Se você recebeu o Nimos por outro caminho que não a nossa página de
> [Releases](../../releases), **não instale** e fale com a gente antes.

---

## macOS

**Requisito:** macOS 13 (Ventura) ou mais novo.

Qual arquivo baixar — menu Apple → *Sobre este Mac*. Os nomes abaixo mostram a versão
atual; na página de Releases, pegue sempre a mais nova.

| O que aparece lá | Arquivo |
|---|---|
| Chip Apple (M1, M2, M3…) | `Nimos_0.1.2_aarch64.dmg` |
| Processador Intel | `Nimos_0.1.2_x64.dmg` |

1. Abra o `.dmg` e arraste o ícone do Nimos para a pasta **Aplicativos**.
2. Abra o Nimos. **O macOS vai bloquear**, dizendo que não foi possível verificar o
   desenvolvedor. É esperado.
3. Vá em **Ajustes do Sistema → Privacidade e Segurança**, role até o fim e clique em
   **"Abrir mesmo assim"**.
4. Confirme. A partir daí o Nimos abre normalmente, sem novo aviso.

### Conferir que o arquivo é o nosso

```bash
shasum -a 256 ~/Downloads/Nimos_0.1.2_aarch64.dmg
```

Compare com a linha correspondente do `SHA256SUMS.txt` publicado junto. Precisa ser
**idêntico**. Se for diferente, apague o arquivo e fale com a gente — é exatamente para
isso que o checksum existe enquanto não há certificado.

---

## Windows

**Requisito:** Windows 10 versão 1803 ou mais novo.

1. Execute `Nimos_0.1.2_x64-setup.exe`.
2. **O SmartScreen vai avisar** que protegeu o computador. Clique em **"Mais informações"**
   e depois em **"Executar assim mesmo"**.
3. Siga o instalador.

### Se o antivírus reclamar

Programa empacotado sem certificado às vezes é marcado como suspeito por heurística, sem
que haja nada de errado com ele.

**Não libere por conta própria.** Avise a gente com o nome do antivírus e a mensagem
exata: nós enviamos o arquivo para análise do fornecedor e voltamos com a orientação.
Liberar na mão esconde o problema para você e deixa todos os outros clientes com ele.

### Conferir que o arquivo é o nosso

```powershell
Get-FileHash .\Nimos_0.1.2_x64-setup.exe -Algorithm SHA256
```

Compare com o `SHA256SUMS.txt`.

---

## Primeira abertura

O Nimos pede uma **chave de ativação** — cinco grupos de cinco caracteres, que o gestor da
sua empresa gera no console e entrega a você.

Ela serve **uma vez só**. Depois de ativado, o app se mantém sozinho: você não precisa
guardar a chave, nem anotá-la, nem digitá-la de novo.

Se a ativação falhar, a mensagem na tela diz o motivo. As três mais comuns:

| Mensagem | O que fazer |
|---|---|
| "Não foi possível falar com o servidor" | é a internet, não a chave. Tente de novo. |
| "Essa chave já foi usada para ativar" | peça outra ao gestor; a anterior foi consumida. |
| "A empresa não tem assentos disponíveis" | o gestor precisa liberar um assento. |

---

## Atualizações

O Nimos se atualiza sozinho. Ao abrir, ele verifica se há versão nova; havendo, mostra um
aviso e você escolhe quando instalar — nunca no meio de um documento.

Você **não** precisa baixar nada aqui de novo, nem reativar, nem reinstalar.

---

## Trocar de computador, formatar, reinstalar

O programa e os seus dados ficam em lugares diferentes:

| | macOS | Windows |
|---|---|---|
| O programa | `/Applications/Nimos.app` | `C:\Program Files\Nimos` |
| Licença e identidade | `~/Library/Application Support/br.com.nimos.desktop` | `%APPDATA%\br.com.nimos.desktop` |
| Cofre (o que permite reverter) | `~/Library/Application Support/Nimos` | `%APPDATA%\Nimos` |

Por isso:

- **Reinstalar por cima** não pede chave nenhuma. O app abre direto, como estava.
- **Trocar de máquina ou formatar** exige uma chave nova — a antiga já foi consumida e
  ninguém consegue mostrá-la de novo, nem o suporte. O gestor gera outra em
  *Usuários → Chave para outro computador*.

> **Ao desinstalar no Windows**, se o instalador perguntar se deve apagar os dados da
> aplicação, pense antes de dizer sim: isso apaga o cofre, e com ele a possibilidade de
> reverter documentos que você já protegeu. A licença também vai junto.

---

## Depois de instalar

Arraste um documento para a janela. Nada é enviado para lugar nenhum: a detecção e a
substituição acontecem na sua máquina, e o mapa que permite reverter fica só neste
computador.

Se a tela inicial avisar que o motor não respondeu, feche e reabra. Persistindo,
reinstale — isso costuma indicar download incompleto.

---

## Desinstalar

- **macOS:** arraste o Nimos da pasta Aplicativos para o Lixo.
- **Windows:** Configurações → Aplicativos → Nimos → Desinstalar.

As duas pastas da tabela acima ficam no computador e podem ser apagadas à parte, se você
quiser remover também o histórico e a licença.
