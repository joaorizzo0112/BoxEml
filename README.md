<div align="center">
  <img src="https://github.com/user-attachments/assets/bfd08729-60c8-4068-910e-d1179e7e0485" alt="Box Emulator" width="160" />
  <h1>Box Emulator</h1>
  
  <p>
    <img src="https://img.shields.io/badge/vers%C3%A3o-0.9.0--dev-00bcd4?style=flat" alt="Versão 0.9.0-dev" />
    <img src="https://img.shields.io/badge/status-em%20andamento-e67e22?style=flat" alt="Em andamento" />
    <img src="https://img.shields.io/badge/linguagem-C%2B%2B17-00599C?style=flat" alt="C++17" />
    <img src="https://img.shields.io/badge/UI-SDL2%20%7C%20Dear%20ImGui-2b3e50?style=flat" alt="SDL2 e Dear ImGui" />
    <img src="https://img.shields.io/badge/n%C3%BAcleo-mGBA%200.11--212--7a12d6d-34495e?style=flat" alt="Núcleo mGBA" />
  </p>

  <p>
    <img src="https://img.shields.io/badge/Windows-passing-4c1?style=flat&logo=github&logoColor=white" alt="Windows" />
    <img src="https://img.shields.io/badge/Linux-passing-4c1?style=flat&logo=github&logoColor=white" alt="Linux" />
    <img src="https://img.shields.io/badge/macOS-passing-4c1?style=flat&logo=github&logoColor=white" alt="macOS" />
  </p>
</div>

Emulador multisistema desenvolvido com foco em desempenho, interface limpa e compatibilidade com consoles clássicos de mesa e portáteis.

> **Nota:** Este projeto ainda está em andamento, caminhando atualmente para a versão **0.9.0**. Novos núcleos, ajustes de compatibilidade e melhorias na interface estão sendo implementados continuamente.
> 
> **Aviso sobre BIOS e ROMs:** O Box Emulator não inclui jogos ou arquivos de BIOS proprietários. Utilize apenas backups legítimos dos seus próprios jogos e firmwares extraídos dos seus aparelhos originais.
---

## Tecnologias e Arquitetura

- **Linguagem:** C++17
- **Janela, Áudio e Entrada:** SDL2
- **Interface Gráfica:** Dear ImGui
- **Núcleo Atual:** mGBA (`0.11-212-7a12d6d`)

---

## Sistemas

A compatibilidade com os consoles abaixo está sendo adicionada gradualmente conforme o projeto avança para a versão **0.9.0**:

### Portáteis

| Console | Formatos |
| :--- | :--- |
| Game Boy | `.gb` |
| Game Boy Color | `.gbc` |
| Game Boy Advance | `.gba` |
| Nintendo DS / DSi | `.nds`, `.dsi` |
| Nintendo 3DS / 2DS | `.3ds`, `.cia` |
| New Nintendo 3DS / New 2DS | `.3ds`, `.cia` |
| Sega Game Gear | `.gg` |
| Atari Lynx | `.lnx` |
| Neo Geo Pocket | `.ngp` |
| Neo Geo Pocket Color | `.ngc` |

### Consoles de Mesa

| Console | Formatos |
| :--- | :--- |
| Nintendo Entertainment System (NES) | `.nes` |
| Famicom Disk System | `.fds` |
| Super Nintendo (SNES) | `.sfc`, `.smc` |
| Nintendo 64 | `.n64`, `.z64`, `.v64` |
| Nintendo Wii | `.iso`, `.wbfs`, `.rvz` |
| Sega Master System | `.sms` |
| Sega SG-1000 | `.sg` |
| Sega 32X | `.32x` |
| Atari 2600 | `.a26`, `.bin` |
| Atari 7800 | `.a78` |
| PC Engine / TurboGrafx-16 | `.pce` |
| PlayStation | `.bin`, `.cue`, `.chd` |
| PlayStation 2 | `.iso`, `.chd` |

---

## Compilação

### Pré-requisitos

- Compilador compatível com **C++17** (GCC, Clang ou MSVC)
- **CMake** (3.16 ou superior)
- Bibliotecas de desenvolvimento do **SDL2**

### Passo a passo

```bash
# Clone o repositório
git clone [https://github.com/joaorizzo0112/box-emulator.git](https://github.com/joaorizzo0112/box-emulator.git)
cd box-emulator

# Configure e compile o projeto
cmake -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build --config Release
```
