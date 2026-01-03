
## In root dir (here /opt/petsc)

For real support:

```bash
sudo python3 ./configure PETSC_ARCH=arch-real --with-scalar-type=real
sudo make PETSC_DIR=/opt/petsc PETSC_ARCH=arch-real all
```

For complex support:`

```bash
sudo python3 ./configure PETSC_ARCH=arch-complex --with-scalar-type=complex
sudo make PETSC_DIR=/opt/petsc PETSC_ARCH=arch-complex all
```


## In conda env

```bash
export PETSC_DIR=/opt/petsc <!-- or wherever your source dir is-->
export PETSC_ARCH=arch-real:arch-complex
pip install petsc4py
```


## Select type in Python PETSc

```python
petsc4py.init(arch='arch-complex') #<!-- or arch-real -->
```

