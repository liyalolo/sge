# sge

qstat -f

/Disk04/Project/Micro/liyanli/A540_BeeMetaGenome/Shell/detail/02.Assembly.megahit/step1.assembly.sh31199qsub
qsub -cwd -l h=tgs-07 -P big -q s1.q Bee-F.sh
qsub -cwd -l h=tgs-16 -P big -q s1.q  Bee-G.sh


qsub -cwd -l h=tgs-18 -q tmp1.q -P tmp1 Bee-A.sh
qsub -cwd -l h=tgs-17 -q tmp1.q -P tmp1 Bee-G.sh
qsub -cwd -l h=tgs-19 -q tmp1.q -P tmp1 Bee-F.sh
qsub -cwd -l h=tgs-20 -q tmp1.q -P tmp1 Bee-F.sh
qsub -cwd -l vf=200g,h=tgs-16 -P big test.sh
qsub -cwd -l vf=300g,h=tgs-16 -P big test.sh


qsub -cwd -l h=tgs-20 -q tmp1.q -P tmp1 -hold_jid 784090  step2.uniqGene.sh

qsub -cwd -l h=tgs-01 -q all.q  test.1.sh

qacc 



