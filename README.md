# xmlfile CLI

Um formatador de XML robusto escrito em C++, projetado para ser rápido e versátil.

## Funcionalidades

- Formatação de arquivos individuais ou em lote.
- Processamento recursivo de diretório.
- Remoção de comentários e textos em branco.
- Controle total sobre indentação e declaração XML.
- Cross-platform: Windows, Linux e Android (aarch64/armv7a).

## Opções

| Curta | Longa | Descrição |
|-------|-------|-----------|
| `-f` | `--file` | Arquivo XML para processar |
| `-b` | `--batch` | Habilitar processamento em lote (usar com `-d`) |
| `-d` | `--dir` | Diretório para processar |
| `-r` | `--recursive` | Processar subdiretórios recursivamente |
| `-i` | `--indent` | Número de espaços para indentação (padrão: 4) |
| `-c` | `--remove-comments` | Remover comentários XML |
| `-s` | `--short-tags` | Usar tags curtas para elementos vazios (padrão: true) |
| `-t` | `--remove-blank-texts` | Remover textos em branco entre tags |
| `-l` | `--remove-empty-lines` | Remover linhas vazias |
| `-e` | `--encoding` | Codificação de saída (padrão: UTF-8) |
| `-u` | `--include-extensions` | Extensões extras (ex: `i3d,gltf`) |
| `-x` | `--non-xml-declaration` | Não incluir declaração XML |
| `-a` | `--standalone` | Adicionar `standalone="yes"` na declaração |
| `-v` | `--version` | Mostrar versão |

## Como Compilar

### Linux
```bash
mkdir build && cd build
cmake ..
make
```

### Windows (Cross-compile no Linux)
```bash
mkdir build_win && cd build_win
cmake .. -DCMAKE_SYSTEM_NAME=Windows -DCMAKE_C_COMPILER=x86_64-w64-mingw32-gcc -DCMAKE_CXX_COMPILER=x86_64-w64-mingw32-g++
make
```

### Android (Cross-compile no Linux)
```bash
mkdir build_android && cd build_android
cmake .. \
  -DCMAKE_TOOLCHAIN_FILE=$ANDROID_NDK_HOME/build/cmake/android.toolchain.cmake \
  -DANDROID_ABI=arm64-v8a \
  -DANDROID_PLATFORM=android-21
make
```

## Dependências
- C++17
- CMake 3.10+
- pugixml (incluído no código-fonte)
