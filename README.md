# MetalPDB XML Parser : A tool to parse xml metalPDB database.

---
## DESCRIPTION
This quick and dirty software parse xml (flat_db_file) MetalPDB database and do some count of histidine protonate state (HIE, HID, ...).
This is based on a parsing process and for statistics part, do your own statistics function.

```text
MetalPDB (http://metalweb.cerm.unifi.it/) is a database providing information on metal binding sites
detected in three-dimensional (3D) structures of biological macromolecules
(Putignano V. et al. Nucleic Acid Res. 2018).
```

Software implemented for 'Interactions et mécanismes d'assemblage des protéines et des peptides' Team, I2BC CNRS UMR 9198.

## Python Compatibility 
This program is compatible with python 3.x.


## Installation

### Installation & usage from sources

1. Clone this repo `git clone https://github.com/jcarvaill/`
2. Install dependancies:

   2.1. Using pip (and use python environment system)
    
      `sudo pip install -r requirements.txt` or `sudo pip3 install -r requirements.txt`
    
 
   2.2. Using virtualenv, suggested (use a virtual environment, leaving your python installation untouched)
    
      - To install virtualenv via pip:
        
        `sudo pip install virtualenv` or `sudo pip3 install virtualenv`

      - To create a virtual environment for aop-helpFinder:
        
        `virtualenv metalPDB_xml_Parser_venv`

      - Don't forget to activate environment with:
        
        `source {PATH}/metalPDB_xml_Parser_venv/bin/activate`

      - (To deactivate environment: `deactivate`)

      - Same as 2.1.

3. Use metalPDB_xml_Parser scripts with `python {PATH}/metalpdb_xml_parser/metalpdb_xml_parser.py` or `python3 {PATH}/metalpdb_xml_parser/metalpdb_xml_parser.py`


## Dependancies and installation: 
Following packages are needed: 
  - argparse
  - argcomplete (for autocompletion, optional)
  - tqdm


## ARGUMENTS 
```text
  -h, --help            show this help message and exit
  -i INPUT, --input INPUT
                        path of the xml file which contain MetalPDB database
  -m METAL, --metal METAL
                        allow to filter database by metal (PDB resname)
                        specified
```

-h, --help
Display help of the software.

`python3 metalpdb_xml_parser.py -h`

### Required arguments:

- -i INPUT, --input INPUT
  
path of the xml file which contain MetalPDB database (flat_db_file.xml)

`python3 metalpdb_xml_parser.py -i flat_db_file_test.xml`

### Optional arguments:

- -m METAL, --metal METAL

allow to filter xml parsed file by a specific metal. You need to specified the metal
to consider (PDB resname):
```text
DDH, BEF, H79, 1PT, AV2, P9G, SNF, CFC, HCB, BF4, CAS, TIL, A72, IR3, HDE, 2J0, RHX, MYQ, PBM, SQ1,
72B, HEG, CON, 0UE, CPO, ALB, RKP, VER, F4S, FMI, DRB, 118, HEM, 3UQ, COB, PLL, ZPT, S31, CPT, CNC,
HEB, IUM, JSE, B1M, PCU, HIF, S32, KSB, CVC, HRU, PCL, 1MK, RHD, AC9, WO3, HEO, V, PT4, H58, F3S,
AM, ALF, DTZ, 31Q, HCO, M43, 0JC, WO5, PT, FCE, CU1, R7U, CU, AMW, 0TE, 8WV, DVW, B9F, A71, I83,
PC4, CBY, RKL, CUL, EU3, DHE, TTO, MD9, PC3, RKM, 51O, ELJ, CL7, WO2, AF3, 6CQ, BVA, N7H, RH3, CUS,
JSD, PD, RE, HEV, TBY, C4R, QHL, XAX, 2GO, MN, DAZ, MM1, CS, MM4, HES, OS, 73M, MM6, CAC, HBF,
SM, NCP, CA, MOS, BVQ, HG, 7G4, HGB, IRI, ART, ZEM, APW, PR, RUA, R6A, HNN, FES, FDD, 35N, DW2,
5IR, GBF, 522, OBV, H57, U1, CL1, PMR, CM2, PB, C7P, NI, HAS, EMT, A6R, GB0, ZN9, 3T3, MGF, VN4,
REJ, CE, IMF, YT3, COY, CSR, BE7, BCB, 4IR, FEC, CAD, UVC, PHG, 2FH, CMH, GA, 0TN, UFE, AUF, BTF,
TB, LOS, RIR, 0H2, AU3, NTE, 6CO, CLA, BA, BAZ, CL0, SR, AIV, MBO, 89R, OMO, OS1, SF3, FLL, 4A6,
LA, IR, TPT, DW5, 3CG, PA0, DY, HE6, EFE, 6B6, 9RU, ZN7, HDD, 5AU, CCH, RU1, CO, HEA, COH, AUC,
4KV, F43, SI4, VN3, HEC, RPS, I42, ME3, HDM, R1Z, HME, FC6, IME, J1R, GD3, 2PT, 3WB, 6BP, RSW, POR,
9QB, RUX, ZNH, AG1, OSV, OFE, CR, 4MO, DWC, CAF, PFC, 9D7, 8AR, FE, MNR, OS4, B13, NA, 3NI, RHE,
RTA, WO4, GIX, B12, CD, ZCM, CM1, RU8, ARS, BOZ, CUP, 4HE, V5A, 9ZQ, C5L, 08T, SIR, YPT, YB2, MOO,
OHX, 7GE, AVC, MP1, LI, SF4, B22, RFB, FCI, ER3, BF2, RUR, B30, MTQ, RU2, 6ZJ, GD, DEF, 3Q7, DW1,
MM5, YBT, YOK, BCL, ASR, I2A, SI7, Y1, CHL, RH, 6O0, SI8, N2R, PTN, REI, B1R, ITM, MOM, SI0, SVP,
RMD, MG, T0M, FE9, 76R, RHM, 2MO, FS1, SI9, 4PU, VVO, 4TI, FE2, TL, UNL, CFQ, 2T8, RBN, MH2, VEA,
NOB, T1A, RU, MMC, 8CY, RKF, MTV, PL1, 6HE, ISW, HE5, PMB, SB, RU7, REP, RTB, ZN6, GCR, REQ, L2D,
AL, 9Q8, 1Y8, HFM, RTC, R1C, CF, MH0, CSB, L4D, L2M, AU, AOH, AG, ZND, DRU, KYT, TTA, CX8, EU,
ATS, 6WO, NRU, HG2, TCN, REO, QPT, SMO, N2W, 3ZZ, DEU, YOL, KYS, NXC, LU, SBO, ZN8, EMC, HKL, R4A,
MM2, 7BU, 0OD, JM1, 6MO, YXX, JSC, HGD, SKZ, BS3, FEL, PNI, HB1, RHL, RML, ZN0, TH, ZN, MSS, YB,
TA0, N2N, RBU, DOZ, NCO, K, RXO, YOM, FDE, LPT, 188, RAX, BJ5, CU6, RUI, IN, SXC, OEY, LSI, CX3,
PCD, RFA, ICA, B6F, MN3, MNH, RUC, M10, MOW, 11R, HNI, 7MT, W, HGI, 1FH, WPC, MAP, R9A, ZN5, 68G,
RUH, RCZ, E52, HO3, MO, 7HE, VO4, FEM, T9T, CB5, HO, 6WF, 3CO, CLN, 5LN, RB, TAS, CQ4, B1Z
```

`python3 metalpdb_xml_parser.py -i flat_db_file_test.xml -m K`

    
## USAGE: 
cd metalpdb_xml_parser/

You can use flat_db_file_test.xml file to test the software.

Command to launch an analyze on MetalPDB database not filtering by specific metal:

 ```text
 python3 metalpdb_xml_parser.py -i flat_db_file_test.xml
```

Command to launch an analyze on Metal PDB database filtering by K (Potassium):

 ```text
 python3 metalpdb_xml_parser.py -i flat_db_file_test.xml -m K
```

by default the results are printed in terminal.

## Licence
This program is under the GNU GPLv3 licence, which means that anyone who 
distributes this code or a derivative work has to make the source available under 
the same terms, and also provides an express grant of patent rights from 
contributors to users.

## Citation
If you use our code for research, please cite metalPDB paper:
```text
@article{putignano2018metalPDB,
  title={MetalPDB in 2018: a database of metal sites in biological macromolecular structures},
  author={Putignano V., Rosato A., Banci L., Andreini C.},
  journal={Nucleic Acid Res. DOI:10.1093/nar/gkx989},
  year={2018}
}
```
