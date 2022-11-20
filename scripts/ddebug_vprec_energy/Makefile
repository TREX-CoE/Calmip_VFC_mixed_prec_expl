NRUNS=1

champ: vfcdd_champ

dd: champ
	rm -rvf dd.line/
	INTERFLOP_DD_NRUNS=${NRUNS} VFC_BACKENDS="libinterflop_vprec.so --precision-binary64=22" vfc_ddebug ddRun_vp ddCmp_vp

dderrors: dd.line/rddmin-cmp/dd.line.exclude
	bash -c "vim -q <(./vfc_dderrors.py ./vmc $<)"

clean:
	rm -rvf dd.line *.ll
