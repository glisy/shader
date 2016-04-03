GlisyShader
===========

## Installation

```sh
$ clib install glisy/shader --save
```

## Usage

```c
#include <glisy/program.h>
#include <glisy/shader.h>
#include <fs/fs.h>

int
main (void) {

  // shader setup time
  GlisyProgram program;
  GlisyShader vertex;
  GlisyShader fragment;

  glisyProgramInit(&program);
  glisyShaderInit(&vertex,
                  GL_VERTEX_SHADER,
                  fs_read(vertexPath));

  glisyShaderInit(&fragment,
                  GL_VERTEX_SHADER,
                  fs_read(fragmentPath));

  glisyProgramAttachShader(&program, &vertex);
  glisyProgramAttachShader(&program, &fragment);
  glisyProgramLink(&program);
  glisyProgramBind(&program);

  return 0;
}
```

## License

MIT
