# JerryScript
- Linguagem: JerryScript
- Nestor Caetano dos Santos - nestorcaetano - 20141011110204 
- Jorge Enrique - JorgeEnrique21  - 20141011110190
- Pedro Oliveira -

## Resumo
- Propósito da linguagem: JerryScript é uma engine super-leve de código aberto altamente otimizada, capaz de rodar javascript de forma a consumir uma baixa quantidade de memória, o que a permite ser utilizada em equipamentos como microcontroladores. A engine suporta compilação no dispositivo, execução e proporciona acesso a periféricos do javascript.
- Paradigma da linguagem: Orientado a objetos
- Data de criação: A engine teve seu código aberto em 2015.
- Principal mantenedor: Criado pela Samsung, hospedado atualmente pela Js foundation com código aberto
## Instalação e uso
~~~~
//construir versão debug para linux
python tools/build.py --debug
//adicionar argumentos personalizados para o Cmake
python tools/build.py --cmake-param=CMAKE_PARAM
//inserir modo de perfil
python tools/build.py --profile=es5.1|es2015-subset|minimal
//usar libc
python tools/build.py --jerry-libc=off
//adicionar arquivo toolchain
python tools/build.py --toolchain=TOOLCHAIN
//usar alocador de memória do sistema
python tools/build.py --system-allocator=on --jerry-libc=off
//ativar 32Bit compressed Pointer
python tools/build.py --cpointer-32bit=on
//mudar tamanho padrão da pilha
python tools/build.py --mem-heap=256
~~~~
~~~~
{
  //Inicializa o uso da engine JerryScript
  jerry_init (JERRY_FLAG_ENABLE_LOG);
  
  //declaram variável do tipo array de caracteres (código do JavaScript)
  char script [] = "print ('Hello, World!');";
  
  //comando "parse" para fazer com que um script seja executado em escopo global
  jerry_parse (script, strlen (script));
  
  //executa código no escopo global
  jerry_run ();

  //acaba a execução do JavaScript para poder liberar memória
  jerry_cleanup ();
}
~~~~


