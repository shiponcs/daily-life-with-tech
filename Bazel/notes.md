1. The root directory of the project is where `WORKSPACE` file is created.
2. All path is **relative** to the root directory.
3. `BUILD` is located per package.
```bash
stage3/
├── lib
│   ├── BUILD
│   ├── hello-time.cc
│   └── hello-time.h
├── main
│   ├── BUILD
│   ├── hello-greet.cc
│   ├── hello-greet.h
│   └── hello-world.cc
└── WORKSPACE
```
Here, `stage3` is the root directory of the project. `lib` and `main` are two packages. 

4. Build a project (from the root of the project)
  ```bash
  build //main:hello-world
  ```
  `//main` says where the `BUILD` file is located and `hello-world` is the target defined inside that `BUILD` file. see `//main` is relative to the directory you ruinning the command from. Note: `//` represents the root directory(where the `WORKSPACE` file is located. 
  
5. (to be continued)
