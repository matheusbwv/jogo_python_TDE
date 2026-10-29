# Jogo de plataforma — Álgebra Linear

Jogo de plataforma em Python baseado no código fornecido na atividade TDE 03. Esta versão mantém o visual original e acrescenta moedas coletáveis e um impulso horizontal.

## Controles

- **A/D** ou **setas**: mover.
- **W**, **seta para cima** ou **espaço**: pular.
- **Shift**: impulso na última direção horizontal, com 1,2 segundo de recarga.
- **R**: reiniciar jogador, inimigo e moedas.
- **Esc**: sair.

Ao tocar o inimigo, jogador e inimigo retornam ao início. As moedas permanecem coletadas até pressionar R. O objetivo original continua fazendo o personagem e o inimigo retornarem ao início.

## Instalação no Windows

Na pasta do projeto, usando o PowerShell:

```powershell
python -m venv venv
.\venv\Scripts\python.exe -m pip install -r requirements.txt
.\venv\Scripts\python.exe .\jogo_algebra_linear.py
```

Os comandos usam diretamente o Python do ambiente virtual, sem precisar ativá-lo ou alterar a política do PowerShell. O projeto usa pygame-ce, compatível com `import pygame` e com Python 3.14.

## Álgebra Linear

- **Moedas:** o código calcula `||p_jogador - p_moeda||`, a norma da diferença entre as posições. Se a distância for menor que o limite, a moeda é coletada.
- **Impulso:** à velocidade do jogador é somado um vetor de direção horizontal multiplicado pela intensidade do impulso: `v_nova = v_movimento + 390 * direção`.
- **Código original:** a posição e a velocidade são vetores; o inimigo usa norma, normalização, produto interno e matriz de rotação para detectar e perseguir o jogador.

O contato com as plataformas foi ajustado para usar posições reais e evitar que o jogador alterne entre estar no chão e no ar devido ao arredondamento de pixels.
