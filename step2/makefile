all: run plot

run:
	for i in `cat POTCAR.spec`; do \
          cat $(VASP_PBE_DIR)/$$i/POTCAR >> POTCAR; \
        done
	cp ../step1/{WAVECAR,CHGCAR} ./
	cp default.wannier90.win wannier90.win
	mpirun vasp-544-s

plot:
	sed "s/data style/ style data/g" -i wannier90_band.gnu
	gnuplot44 -p wannier90_band.gnu

clean:
	rm CHG CHGCAR CONTCAR DOSCAR EIGENVAL IBZKPT OSZICAR OUTCAR PCDAT POTCAR PROCAR REPORT vasprun.xml wannier90* WAVECAR XDATCAR -f
