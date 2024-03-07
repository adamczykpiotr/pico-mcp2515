Raspberry Pi Pico MCP2515 CAN interface library
---------------------------------------------------------
This Raspberry Pi Pico library is a ported & optimized version of the magnificent library [arduino-mcp2515](https://github.com/autowp/arduino-mcp2515) by [autowp](https://github.com/autowp).

## Optimization

This library was optimized to use SPI transfer of multiple bytes in a single function call. This is contrary to the original code where ```for``` loop was heavily used. Theese optimizations might seem insignificant as they shave only few microseconds each time but they surely add up. If the only goal of the microcontroller is to poll CAN-Bus frames, the speedup can reach roughly from 20 to 40% depending on frame byte count!

Benchmark used with frame polling:
| Frame bytes | Before [µs] |	After [µs] | Speedup [%] |
| ----------- | ----------- | ---------- | ----------- |
| 0           | 35          |	29	       | 22.8        |
| 1           | 37          |	29	       | 21.6        |
| 2           | 39          |	30	       | 30.0        |
| 3           | 41          |	31	       | 32.3        |
| 4           | 43          |	32	       | 34.4        |
| 5           | 45          |	33	       | 36.4        |
| 6           | 47          |	34	       | 38.2        |
| 7           | 49          |	35	       | 40.0        |
| 8           | 51          |	36	       | 41.7        |
| Average     | 43          |	31.9       | 33.0        |

----

This software is written by loovee ([luweicong@seeed.cc](luweicong@seeed.cc "luweicong@seeed.cc")) for seeed studio, updated by Dmitry ([https://github.com/autowp](https://github.com/autowp "https://github.com/autowp")) and then ported by Piotr Adamczyk [https://github.com/adamczykpiotr](https://github.com/adamczykpiotr) and is licensed under [The MIT License](http://opensource.org/licenses/mit-license.php). Check [LICENSE.md](LICENSE.md) for more information.

Contributing to this software is warmly welcomed. You can do this basically by [forking](https://help.github.com/articles/fork-a-repo), committing modifications and then [pulling requests](https://help.github.com/articles/using-pull-requests) (follow the links above for operating guide). Adding change log and your contact into file header is encouraged. Thanks for your contribution.

Seeed Studio is an open hardware facilitation company based in Shenzhen, China. Benefiting from local manufacture power and convenient global logistic system,
we integrate resources to serve new era of innovation. Seeed also works with global distributors and partners to push open hardware movement
