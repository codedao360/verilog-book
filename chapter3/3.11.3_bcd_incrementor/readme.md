
3.11.3 BCD Incrementor
----------------------

### Page 81

#### Structure of the test circuit
```
                   digit2      digit1       digit0
                    +            +            +
                    |            |            |
                    |            |            |
           +------------------------------------------+
carry_led  |        |            |            |       |
           |     +--v--+      +--v--+      +--v--+    |
     <-----------+ bcd <------+ bcd <------+ bcd <-+  |  3-digit
           |     | unit| carry| unit| carry| unit| |  |
           |     +--+--+      +--+--+      +--+--+ +  |  incrementor
           |        |            |            |    1  |
           +------------------------------------------+
            +-------+            |            +------+
            |                    |                   |
    +-------v---------+ +--------v--------+ +--------v--------+
    |                 | |                 | |                 |
    |   bcd_to_sseg   | |   bcd_to_sseg   | |   bcd_to_sseg   |
    |                 | |                 | |                 |
    +---------+-------+ +--------+--------+ +--------+--------+
              |                  | led1              |
        led2  +------------+     |     +-------------+  led0
                         +-v-----v-----v-+
                         |               |
              clk +------>   disp_mux    |
                         |               |
                         +----+-----+----+
                              |     |
                              |     |
                              v     v
                             sseg   an

```