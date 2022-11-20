NRUNS=1

champ: vfcdd_champ

dd: champ
	rm -rf dd.line/
	#INTERFLOP_DD_NRUNS=${NRUNS} VFC_BACKENDS="libinterflop_mca.so ${MCA_MODE}" vfc_ddebug ddRun ddCmp
	INTERFLOP_DD_NRUNS=${NRUNS} VFC_BACKENDS="libinterflop_vprec.so --precision-binary64=24" vfc_ddebug ddRun ddCmp

dderrors: dd.line/rddmin-cmp/dd.line.exclude
	bash -c "vim -q <(./vfc_dderrors.py ./vmc $<)"

clean:
	rm -rf dd.line *.ll
