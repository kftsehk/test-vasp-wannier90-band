all:
	for i in `cat POTCAR.spec`; do \
          cat $(VASP_PBE_DIR)/$$i/POTCAR >> POTCAR; \
        done
	for i in `seq 1 1 5`; do \
          mpirun -ppn 4 vasp-544-s; \
          cp CONTCAR POSCAR; \
        done

clean:
	rm CHG CHGCAR CONTCAR DOSCAR EIGENVAL IBZKPT OSZICAR OUTCAR PCDAT POTCAR PROCAR REPORT vasprun.xml WAVECAR XDATCAR -f
