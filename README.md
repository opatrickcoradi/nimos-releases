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

## Instalar

O passo a passo completo — incluindo como passar pelo aviso do sistema, conferir o
checksum e o que fazer ao trocar de computador — está em
**[INSTALACAO.md](INSTALACAO.md)**.

O resumo: baixe o arquivo da sua plataforma, confira o SHA-256 contra o
`SHA256SUMS.txt` que acompanha, e abra. Na primeira vez o sistema vai pedir confirmação,
porque o instalador ainda não tem certificado de assinatura.

Depois de instalado, o Nimos se atualiza sozinho. Você não precisa voltar aqui.
