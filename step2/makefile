all: run plot

run:
	for i in `cat POTCAR.spec`; do \
          cat $(VASP_PBE_DIR)/$$i/POTCAR >> POTCAR; \
        done
	cp ../step1/CHGCAR ./
	mpirun -ppn 4 vasp-544-s

plot:
	python bands_Si.py &

clean:
	rm CHG CHGCAR CONTCAR DOSCAR EIGENVAL IBZKPT OSZICAR OUTCAR PCDAT POTCAR PROCAR REPORT vasprun.xml wannier90* WAVECAR XDATCAR -f
