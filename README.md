# Instaladores do Nimos

O Nimos anonimiza documentos **no seu computador**, antes que eles sejam enviados a
ferramentas de IA. Nenhum documento sai da máquina.

Este repositório tem só os arquivos de instalação. O código-fonte é privado.

## Baixar

Os instaladores estão em [Releases](../../releases). Pegue sempre a versão mais recente:

| Sistema | Arquivo |
|---|---|
| macOS (Apple Silicon — M1 em diante) | `Nimos_X.Y.Z_aarch64.dmg` |
| macOS (Intel) | `Nimos_X.Y.Z_x64.dmg` |
| Windows | `Nimos_X.Y.Z_x64-setup.exe` |

## Confira o arquivo antes de instalar

O Nimos ainda não tem certificado de assinatura, então o sistema vai pedir confirmação ao
abrir. O checksum é o que permite ter certeza de que o arquivo é o que publicamos — e não
algo trocado no caminho.

Cada release traz um `SHA256SUMS.txt`. Para conferir:

```bash
# macOS e Linux
shasum -a 256 Nimos_0.1.1_aarch64.dmg
```

```powershell
# Windows
Get-FileHash Nimos_0.1.1_x64-setup.exe -Algorithm SHA256
```

O valor precisa bater com a linha correspondente do `SHA256SUMS.txt`. Se não bater, **não
instale** e fale conosco.

## Primeira abertura

**macOS:** o sistema vai dizer que o app não pôde ser verificado. Vá em *Configurações do
Sistema → Privacidade e Segurança*, role até o aviso sobre o Nimos e clique em *Abrir
mesmo assim*.

**Windows:** o SmartScreen vai mostrar "O Windows protegeu o computador". Clique em *Mais
informações* e depois em *Executar assim mesmo*.

Os dois acontecem porque o instalador não tem certificado — não porque haja algo errado
com o arquivo. É o que o checksum acima serve para confirmar.

## Ativação

Na primeira abertura o app pede uma chave de ativação, que o gestor da sua empresa gera
no console. Ela serve uma vez só; depois disso o app se mantém sozinho e não pede mais
nada. Atualizações chegam automaticamente.
