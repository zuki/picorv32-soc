# picorv32 socのMAX1000への実装

[https://github.com/oscourse-tsinghua/undergraduate-zwpu2019](https://github.com/oscourse-tsinghua/undergraduate-zwpu2019)による

## メモリマップ

| モジュール | メモリ | サイズ |
| ----------| --------- | ----- |
| ROM      |  0x0000_0000 ~ 0x0000_7fff  | 32 KB |
| SDRAM    |  0x0100_0000 - 0x017f_ffff  | 8 MB |
| UART      |  0x0200_0000 ~ 0x0200_001f  | 32 Bytes |
| LED      |  0x0300_0000 ~ 0x0300_000f  | 16 Bytes |

## 各種ポインタレジスタの設定

|  レジスタ | アドレス |
| ----------| ---------|
| gp        | 0x0100_0800 |
| tp        | 0x0100_0800 |
| sp        | 0x0180_0000 |


## UARTメモリマップ

| モジュール | メモリ | 注記 |
| ----------| --------- | ----- |
| INPORT    | 0x0200_0000 | |
| OUTPORT   | 0x0200_0004 | |
| STATUS    | 0x0200_0008 | |
| DIVIDER   | 0x0200_0010 | Start.Sで設定 |

### UARTメモリ詳細

[Embedded Peripherals IP User Guide](https://www.intel.com/content/dam/www/programmable/us/en/pdfs/literature/ug/ug_embedded_ip.pdf) `11. UART Core`のTable 96 (p.138)
