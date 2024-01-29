# Send-Data-via-RF-with-Cheap-RF-Modules
Roman Black's article using Run Length Encoding was the Inspiration

I stumbled across Roman Black's article on using cheap RF modules for transmitting data. While the world has come a long way in the 10 years since Roman wrote about his findings those modules, and more modern ones at similar modest cost, are widely available. https://www.romanblack.com/RF/cheapRFmodules.htm

The concept had my hooked immediately. It uses RF It was really well written and comprehensive Seemed like an ideal project that will enable other projects. I get a thrill out of using STM8 eForth. You should try it too.

My broad goal was a burst transmission of one to three bytes of data with long off periods. This required some maths to understand the tradeoff between battery life, data speed and preamble length. At present I am using a "pedestrian" data rate, (uS shown is measured):

Preamble Pulse 5 units high to help the RX adjust gain (560uS)
Start pulse is 3 units low, 2 units high. (560uS)
Zero is one unit low, one unit high,and (298uS)
One is two units low, one unit high       (410uS)

Each byte takes about 4ms to send and for testing I spaced them 500ms apart. In practice I expect I will send a packet of 1-3 bytes, repeated several times say 20ms apart before going into a long sleep.

You can read more details on the develpoment process at https://vk6tt.blogspot.com/search/label/RLE Data via RF Modules
