# Battery Charge-Discharge Voltage Curves Dataset

![Battery charge-discharge voltage curves](BCDC.png)

## Overview

This dataset contains raw voltage time-series measurements collected during charge and discharge tests on ten rechargeable LiFePO4 battery cells. It includes five Lithium Werks APR cells and five BSE LiFePO4 cells. For each battery, three charge curves were recorded under a constant-current/constant-voltage (CCCV) charging procedure, and three discharge curves were recorded under constant-current discharge regimes.

The dataset can support battery capacity estimation, voltage-curve comparison, and validation of equivalent-circuit or data-driven battery models.

## Dataset Summary

| Item | Description |
|---|---|
| Dataset title | Charge and discharge voltage curves for APR and BSE rechargeable batteries under CCCV charging and three constant-current discharge profiles |
| Chemistry | LiFePO4 / lithium iron phosphate |
| Number of batteries | 10 |
| Number of charge curves | 30 |
| Number of discharge curves | 30 |
| Total voltage curves | 60 |
| Main data format | XLSX workbook |
| Time unit | hours `[h]` |
| Voltage unit | volts `[V]` |
| Sampling interval | 1 second |
| Ambient temperature | 23 °C ± 2 °C |
| Ambient relative humidity | 65 ± 20% RH |
| Charge profile | CCCV |
| Discharge profiles | C1/1, C2/2, C3/3 |

## Workbook Structure

The workbook contains one metadata sheet and 20 data sheets.

### Metadata Sheet

| Sheet | Description |
|---|---|
| `Header` | Dataset description, authors, license, battery metadata, equipment, test conditions, and acronym definitions. |

### Data Sheets

Each battery has one charge sheet and one discharge sheet.

| Sheet pattern | Meaning |
|---|---|
| `CHG-*` | Charge curves for one battery. |
| `DCHG-*` | Discharge curves for one battery. |

The workbook sheets are:

- `CHG-APREH171000701957`, `DCHG-APREH171000701957`
- `CHG-APREH171000707901`, `DCHG-APREH171000707901`
- `CHG-APREH171000711199`, `DCHG-APREH171000711199`
- `CHG-APREH171000711443`, `DCHG-APREH171000711443`
- `CHG-APREH171000714657`, `DCHG-APREH171000714657`
- `CHG-BSE001`, `DCHG-BSE001`
- `CHG-BSE002`, `DCHG-BSE002`
- `CHG-BSE003`, `DCHG-BSE003`
- `CHG-BSE004`, `DCHG-BSE004`
- `CHG-BSE005`, `DCHG-BSE005`

## CSV Archive Structure

In addition to the Excel workbook, the dataset is also provided as a CSV archive for easier programmatic analysis.

The CSV archive contains 20 data CSV files, corresponding to the 20 charge/discharge data sheets in the workbook. The CSV files exclude the workbook metadata `Header` sheet. However, each CSV file still contains column names for the measured time-voltage data.

### CSV File Naming Convention

| Filename pattern | Meaning |
|---|---|
| `charge_discharge_voltage_curves__chg_*.csv` | Charge data for one battery. |
| `charge_discharge_voltage_curves__dchg_*.csv` | Discharge data for one battery. |
| `apreh...` in filename | APR/Lithium Werks battery serial identifier. |
| `bse001` to `bse005` in filename | BSE battery identifier. |

### CSV Files Included

- `charge_discharge_voltage_curves__chg_apreh171000701957.csv`
- `charge_discharge_voltage_curves__chg_apreh171000707901.csv`
- `charge_discharge_voltage_curves__chg_apreh171000711199.csv`
- `charge_discharge_voltage_curves__chg_apreh171000711443.csv`
- `charge_discharge_voltage_curves__chg_apreh171000714657.csv`
- `charge_discharge_voltage_curves__chg_bse001.csv`
- `charge_discharge_voltage_curves__chg_bse002.csv`
- `charge_discharge_voltage_curves__chg_bse003.csv`
- `charge_discharge_voltage_curves__chg_bse004.csv`
- `charge_discharge_voltage_curves__chg_bse005.csv`
- `charge_discharge_voltage_curves__dchg_apreh171000701957.csv`
- `charge_discharge_voltage_curves__dchg_apreh171000707901.csv`
- `charge_discharge_voltage_curves__dchg_apreh171000711199.csv`
- `charge_discharge_voltage_curves__dchg_apreh171000711443.csv`
- `charge_discharge_voltage_curves__dchg_apreh171000714657.csv`
- `charge_discharge_voltage_curves__dchg_bse001.csv`
- `charge_discharge_voltage_curves__dchg_bse002.csv`
- `charge_discharge_voltage_curves__dchg_bse003.csv`
- `charge_discharge_voltage_curves__dchg_bse004.csv`
- `charge_discharge_voltage_curves__dchg_bse005.csv`

The CSV files are intended for direct use in Python, MATLAB, R, or other analysis software. For full dataset metadata, battery specifications, authorship, equipment, and test conditions, users should refer to the Excel workbook `Header` sheet or this README file.

## Data Column Format

Each data sheet contains three timestamp-voltage column pairs.

### Charge Sheets

| Column | Example | Description |
|---|---|---|
| `Timestamp_1 [h]` | time in hours | Timestamp for charge run 1. |
| `BATT_001_CC1 [V]` | voltage in volts | Battery voltage for charge run 1. |
| `Timestamp_2 [h]` | time in hours | Timestamp for charge run 2. |
| `BATT_001_CC2 [V]` | voltage in volts | Battery voltage for charge run 2. |
| `Timestamp_3 [h]` | time in hours | Timestamp for charge run 3. |
| `BATT_001_CC3 [V]` | voltage in volts | Battery voltage for charge run 3. |

### Discharge Sheets

| Column | Example | Description |
|---|---|---|
| `Timestamp_1 [h]` | time in hours | Timestamp for discharge run 1. |
| `BATT_001_DC1 [V]` | voltage in volts | Battery voltage for discharge run 1. |
| `Timestamp_2 [h]` | time in hours | Timestamp for discharge run 2. |
| `BATT_001_DC2 [V]` | voltage in volts | Battery voltage for discharge run 2. |
| `Timestamp_3 [h]` | time in hours | Timestamp for discharge run 3. |
| `BATT_001_DC3 [V]` | voltage in volts | Battery voltage for discharge run 3. |

The battery identifier changes from `BATT_001` to `BATT_010` depending on the tested cell.

## Battery Metadata

| Battery IDs | Cell group | Manufacturer | Chemistry | Nominal capacity | Nominal voltage | Internal resistance |
|---|---|---|---|---:|---:|---:|
| `BATT_001`-`BATT_005` | APR | Lithium Werks | LiFePO4 | 1100 mAh | 3.3 V | 12.6 mOhm |
| `BATT_006`-`BATT_010` | BSE | BSE | LiFePO4 | 1500 mAh | 3.2 V | 35 mOhm |

APR cell serial numbers included in the workbook are:

- `BATT_001`: EH171000701957
- `BATT_002`: EH171000707901
- `BATT_003`: EH171000711199
- `BATT_004`: EH171000711443
- `BATT_005`: EH171000714657

BSE cells are identified in the workbook as `BSE001` to `BSE005`.

## Experimental Procedure

The recorded tests follow the sequence documented in the workbook metadata:

1. Charge using CCCV.
2. Rest for 1 hour.
3. Discharge using the first constant-current profile.
4. Rest for 1 hour.
5. Charge using CCCV.
6. Discharge using the second constant-current profile.
7. Rest for 1 hour.
8. Charge using CCCV.
9. Rest for 1 hour.
10. Discharge using the third constant-current profile.

APR cells use a standard charge condition of 3.6 V, 1C, with termination current below 50 mA, and a standard discharge condition of 2.0 V at 0.2C.

BSE cells use a charge condition of 3.65 V, 1C, with termination current below 15 mA, and a standard discharge condition of 2.5 V at 0.2C.

## Equipment

| Equipment ID | Type | Manufacturer | Model / Description |
|---|---|---|---|
| `EQ_001` | DC power supply | Tenma | 72-2535 |
| `EQ_002` | DC electronic load | Tenma | 72-13200 |
| `EQ_003` | Thermal chamber | Custom-built |
| `EQ_004` | Data acquisition system | National Instruments | NI USB-6251 |
| `EQ_005` | Personal computer | HP | ProDesk 400G7 |

## Suggested Use Cases

This dataset may be used for:

- Charge and discharge voltage-curve analysis.
- Effective capacity estimation.
- Battery consistency and cell-to-cell comparison.
- Validation of battery equivalent-circuit models.
- Training or benchmarking data-driven battery models.
- Visualization of LiFePO4 charge/discharge behavior.

## Basic Data-Loading Notes

When processing the workbook programmatically:

1. Read the `Header` sheet first to extract metadata.
2. Iterate through sheets beginning with `CHG-` and `DCHG-`.
3. Treat each pair of columns as one curve: timestamp plus voltage.
4. Drop empty rows independently for each timestamp-voltage pair, because different curves may have different lengths.
5. Use the timestamp columns in hours and voltage columns in volts.

## Data Quality Notes

- The dataset contains raw measured voltage time series.
- Charge and discharge sheets may have different numbers of rows depending on curve duration.
- Timestamp values are reported in hours.
- Voltage values are reported in volts.
- Rest periods and procedure details are described in the metadata sheet, while the main data sheets contain the measured curves.

## Authors and Contributors

- VOICILA Iulian-Teodor
- ENACHE Bogdan-Adrian
- VILCIU Irina
- SERITAN George-Calin

## Institution

National University of Science and Technology POLITEHNICA Bucharest

## Contact

For questions about the dataset, contact: `iulian.voicila@upb.ro`

## Related Publication

Voicila, T. I., Enache, B. A., Mateescu, M. V., Seritan, G. C. (2025). *A high-speed multi-chemistry and multi-battery state-of-health screening system for retired lithium-ion batteries*. University POLITEHNICA of Bucharest Scientific Bulletin Series C - Electrical Engineering and Computer Science, 87(3). WOS:001562110500021.

## License

Creative Commons Attribution 4.0 International (CC BY 4.0).

Users should cite the dataset and the related publication when using this data.
