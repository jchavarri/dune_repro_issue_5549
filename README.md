## Dune repro issue 5549

1. Install switch: `make create-switch`

2. Run Dune in watch mode: `dune build -w @all`, notice how the build leverages all cores in cpu.

3. Modify `chunk2/dir_2_1/m2_1_1_1.ml` and `mli`, notice how the build finishes very fast, even if a few modules depend on it.

4. Modify `chunk1/dir_1_1/m1_1_1_1.ml` and `mli`, notice how the build only executes 1 job at a time.
