## Scenario

Review the following scenario. Then complete the step-by-step instructions.

You work as a security analyst for a travel agency that advertises sales and promotions on the company’s website. The employees of the company regularly access the company’s sales webpage to search for vacation packages their customers might like.

One afternoon, you receive an automated alert from your monitoring system indicating a problem with the web server. You attempt to visit the company’s website, but you receive a connection timeout error message in your browser.

You use a packet sniffer to capture data packets in transit to and from the web server. You notice a large number of TCP SYN requests coming from an unfamiliar IP address. The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests. You suspect the server is under attack by a malicious actor.

You take the server offline temporarily so that the machine can recover and return to a normal operating status. You also configure the company’s firewall to block the IP address that was sending the abnormal number of SYN requests. You know that your IP blocking solution won’t last long, as an attacker can spoof other IP addresses to get around this block. You need to alert your manager about this problem quickly and discuss the next steps to stop this attacker and prevent this problem from happening again. You will need to be prepared to tell your boss about the type of attack you discovered and how it was affecting the web server and employees.

## Step-By-Step Instructions

Follow the instructions and answer the question to complete the activity.

|   No. |     Time | Source        | Destination   | Protocol   | Info                                            |
|------:|---------:|:--------------|:--------------|:-----------|:------------------------------------------------|
|    47 |  3.14452 | 198.51.100.23 | 192.0.2.1     | TCP        | 42584->443 [SYN] Seq=0 Win-5792 Len=120...      |
|    48 |  3.19576 | 192.0.2.1     | 198.51.100.23 | TCP        | 443->42584 [SYN, ACK] Seq=0 Win-5792 Len=120... |
|    49 |  3.24699 | 198.51.100.23 | 192.0.2.1     | TCP        | 42584->443 [ACK] Seq=1 Win-5792 Len=120...      |
|    50 |  3.29822 | 198.51.100.23 | 192.0.2.1     | HTTP       | GET  /sales.html HTTP/1.1                       |
|    51 |  3.34946 | 192.0.2.1     | 198.51.100.23 | HTTP       | HTTP/1.1 200 OK (text/html)                     |
|    52 |  3.39069 | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    53 |  3.44193 | 192.0.2.1     | 203.0.113.0   | TCP        | 443->54770 [SYN, ACK] Seq=0 Win-5792 Len=120... |
|    54 |  3.49316 | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [ACK Seq=1 Win=5792 Len=0...         |
|    55 |  3.54439 | 198.51.100.14 | 192.0.2.1     | TCP        | 14785->443 [SYN] Seq=0 Win-5792 Len=120...      |
|    56 |  3.59963 | 192.0.2.1     | 198.51.100.14 | TCP        | 443->14785 [SYN, ACK] Seq=0 Win-5792 Len=120... |
|    57 |  3.66486 | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    58 |  3.7301  | 198.51.100.14 | 192.0.2.1     | TCP        | 14785->443 [ACK] Seq=1 Win-5792 Len=120...      |
|    59 |  3.79533 | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win-5792 Len=120...      |
|    60 |  3.86057 | 198.51.100.14 | 192.0.2.1     | HTTP       | GET  /sales.html HTTP/1.1                       |
|    61 |  3.9395  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win-5792 Len=120...      |
|    62 |  4.01843 | 192.0.2.1     | 198.51.100.14 | HTTP       | HTTP/1.1 200 OK (text/html)                     |
|    63 |  4.09736 | 198.51.100.5  | 192.0.2.1     | TCP        | 33638->443 [SYN] Seq=0 Win-5792 Len=120...      |
|    64 |  4.17629 | 192.0.2.1     | 203.0.113.0   | TCP        | 443->54770 [SYN, ACK] Seq=0 Win-5792 Len=120... |
|    65 |  4.25523 | 192.0.2.1     | 198.51.100.5  | TCP        | 443->33638 [SYN, ACK] Seq=0 Win-5792 Len=120... |
|    66 |  4.25616 | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    67 |  5.23509 | 198.51.100.5  | 192.0.2.1     | TCP        | 33638->443 [ACK] Seq=1 Win-5792 Len=120...      |
|    68 |  5.23602 | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    69 |  5.23695 | 198.51.100.16 | 192.0.2.1     | TCP        | 32641->443 [SYN] Seq=0 Win-5792 Len=120...      |
|    70 |  5.23789 | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    71 |  6.22873 | 198.51.100.5  | 192.0.2.1     | HTTP       | GET  /sales.html HTTP/1.1                       |
|    72 |  6.22964 | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    73 |  6.23055 | 192.0.2.1     | 198.51.100.16 | TCP        | 443->32641 [RST, ACK] Seq=0 Win-5792 Len=120... |
|    74 |  6.33054 | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    75 |  6.33088 | 198.51.100.7  | 192.0.2.1     | TCP        | 42584->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    76 |  6.33123 | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    77 |  7.33058 | 192.0.2.1     | 198.51.100.5  | TCP        | HTTP/1.1 504 Gateway Time-out (text/html)       |
|    78 |  7.35132 | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    79 |  7.36077 | 198.51.100.22 | 192.0.2.1     | TCP        | 6345->443 [SYN] Seq=0 Win=5792 Len=0...         |
|    80 |  7.38077 | 192.0.2.1     | 198.51.100.7  | TCP        | 443->42584 [RST, ACK] Seq=1 Win-5792 Len=120... |
|    81 |  7.38088 | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    82 |  7.38388 | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    83 |  7.48275 | 192.0.2.1     | 203.0.113.0   | TCP        | 443->54770 [RST, ACK] Seq=1 Win=5792 Len=0...   |
|    84 |  7.58163 | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    85 |  7.6805  | 192.0.2.1     | 198.51.100.22 | TCP        | 443->6345 [RST, ACK] Seq=1 Win=5792 Len=0...    |
|    86 |  7.70938 | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    87 |  7.73824 | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    88 |  7.7671  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    89 | 13.896   | 192.0.2.1     | 203.0.113.0   | TCP        | 443->54770 [RST, ACK] Seq=1 Win=5792 Len=0...   |
|    90 | 13.9198  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    91 | 13.9437  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    92 | 13.9676  | 192.0.2.1     | 198.51.100.16 | TCP        | 443->32641 [RST, ACK] Seq=1 Win-5792 Len=120... |
|    93 | 13.9914  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    94 | 14.0152  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    95 | 14.4391  | 192.0.2.1     | 203.0.113.0   | TCP        | 443->54770 [RST, ACK] Seq=1 Win=5792 Len=0...   |
|    96 | 14.8629  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    97 | 14.8867  | 198.51.100.9  | 192.0.2.1     | TCP        | 4631->443 [SYN] Seq=0 Win=5792 Len=0...         |
|    98 | 15.3106  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|    99 | 15.7344  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   100 | 16.1582  | 192.0.2.1     | 203.0.113.0   | TCP        | 443->54770 [RST, ACK] Seq=1 Win=5792 Len=0...   |
|   101 | 16.582   | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   102 | 17.0059  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   103 | 17.4297  | 192.0.2.1     | 203.0.113.0   | TCP        | 443->54770 [RST, ACK] Seq=1 Win=5792 Len=0...   |
|   104 | 17.4527  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   105 | 17.4757  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   106 | 17.4987  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   107 | 17.5217  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   108 | 17.5448  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   109 | 17.5678  | 192.0.2.1     | 203.0.113.0   | TCP        | 443->54770 [RST, ACK] Seq=1 Win=5792 Len=0...   |
|   110 | 17.5908  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   111 | 18.4138  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   112 | 18.4368  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   113 | 18.4598  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   114 | 18.4828  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   115 | 18.5067  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   116 | 18.5297  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   117 | 18.5527  | 192.0.2.1     | 203.0.113.0   | TCP        | 443->54770 [RST, ACK] Seq=1 Win=5792 Len=0...   |
|   118 | 18.8757  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   119 | 19.1987  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   120 | 19.5217  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   121 | 19.8447  | 192.0.2.1     | 198.51.100.9  | TCP        | 443->4631 [RST, ACK] Seq=1 Win=5792 Len=0...    |
|   122 | 20.1677  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   123 | 20.4908  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   124 | 20.8138  | 192.0.2.1     | 203.0.113.0   | TCP        | 443->54770 [RST, ACK] Seq=1 Win=5792 Len=0...   |
|   125 | 21.1368  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   126 | 21.4598  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   127 | 21.7828  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   128 | 22.1058  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   129 | 22.4288  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   130 | 22.7518  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   131 | 23.0749  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   132 | 23.3979  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   133 | 23.7209  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   134 | 24.0439  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   135 | 24.3669  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   136 | 24.6899  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   137 | 25.0129  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   138 | 25.336   | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   139 | 25.659   | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   140 | 25.982   | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   141 | 26.305   | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   142 | 26.628   | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   143 | 26.951   | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   144 | 27.274   | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   145 | 27.597   | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   146 | 27.9201  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   147 | 28.2431  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   148 | 28.5661  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   149 | 28.8891  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   150 | 29.2121  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   151 | 29.5351  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   152 | 29.8581  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   153 | 30.1811  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   154 | 30.5042  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   155 | 30.8272  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   156 | 31.1502  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   157 | 31.4732  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   158 | 31.7962  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   159 | 32.1192  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   160 | 32.4422  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   161 | 32.7653  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   162 | 33.0883  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   163 | 33.4113  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   164 | 33.7343  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   165 | 34.0573  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   166 | 34.3803  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   167 | 34.7033  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   168 | 35.0263  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   169 | 35.3494  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   170 | 35.6724  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   171 | 35.9954  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   172 | 36.3184  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   173 | 36.6414  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   174 | 36.9644  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   175 | 37.2874  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   176 | 37.6104  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   177 | 37.9335  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   178 | 38.2565  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   179 | 38.5795  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   180 | 38.9025  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   181 | 39.2255  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   182 | 39.5485  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   183 | 39.8715  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   184 | 40.1946  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   185 | 40.5176  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   186 | 40.8406  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   187 | 41.1636  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   188 | 41.4866  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   189 | 41.8096  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   190 | 42.1326  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   191 | 42.4556  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   192 | 42.7787  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   193 | 43.1017  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   194 | 43.4247  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   195 | 43.7477  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   196 | 44.0707  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   197 | 44.3937  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   198 | 44.7167  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   199 | 45.0397  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   200 | 45.3628  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   201 | 45.6858  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   202 | 46.0088  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   203 | 46.3318  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   204 | 46.6548  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   205 | 46.9778  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   206 | 47.3008  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   207 | 47.6238  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   208 | 47.9469  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   209 | 48.2699  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   210 | 48.5929  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   211 | 48.9159  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   212 | 49.2389  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   213 | 49.5619  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   214 | 49.8849  | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   214 | 50.208   | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   214 | 50.531   | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   214 | 50.854   | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   214 | 51.177   | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   214 | 51.5     | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |
|   214 | 51.823   | 203.0.113.0   | 192.0.2.1     | TCP        | 54770->443 [SYN] Seq=0 Win=5792 Len=0...        |


### 1. Identify the type of attack causing this network interruption

Reflect on the types of network intrusion attacks that you have learned about in this course so far. 
As a security analyst, identifying the type of network attack based on the incident is the first step to managing the attack and preventing similar attacks in the future.

Here are some questions to consider when determining what type of attack occurred:

- What do you currently understand about network attacks?
- Which type of attack would likely result in the symptoms described in the scenario?
- What is the difference between a denial of service (DoS) and distributed denial of service (DDoS)?
- Why is the website taking a long time to load and reporting a connection timeout error?

#### Answers:

- **What do you currently understand about network attacks?**

  Network attacks are typically carried out by malicious agents seeking some form of benefit, creating a disruptive effect on networks, devices, and operations of an organization/entity.
  Common attacks are often made via Malware, Spoofing, Packet Sniffing, and Packet Flooding, which can lead to the extraction of confidential and valuable information, damage to reputation, and financial loss.
  Examples of attacks used include DoS, DDoS, SYN, or ICMP Flooding, and Ping of Death.

- **Which type of attack would likely result in the symptoms described in the scenario?**

  Analyzing the exercise, I noticed that after using a packet sniffer to analyze the data packets, a large number of TCP SYN requests were revealed coming from an unknown IP address. Therefore, the likelihood of it being a Direct DoS SYN Flood Attack is very high and is the most probable cause.

- **What is the difference between a denial of service (DoS) and distributed denial of service (DDoS)?**

  In a DoS situation, a single source is used for attacking a target, whereas in a DDoS situation, multiple sources are used to attack a target.

- **Why is the website taking a long time to load and reporting a connection timeout error?**

  Since SYN packets are sent very frequently, multiplying several connection requests, the server becomes overwhelmed because the number of SYN requests exceeds the number of open ports to handle so many requests.
  The HTTP/1.1 504 Gateway Time-out (text/html) error is sent because the server takes too long to respond, and the [RST, ACK] packet is sent if the [SYN, ACK] request does not happen, canceling that request.

### Section 1: Identify the type of attack that may have caused this network interruption

**One potential explanation for the website's connection timeout error message is:**

As the attacker sends a large number of SYN Packets to the target, the server that receives them tries to respond to each request, leaving the port open for receiving the response. 
Since it cannot respond to all, the port remains open in standby waiting for the [ACK] packet, which will never arrive. 
The server is disrupted by its inability to respond, sending timeout errors.

**The logs show that:**

The logs show that initially the [SYN] request is successfully responded to, but progressively the attacker starts a process of flooding with SYN requests, and the server becomes unable to operate normally.

**This event could be:**

Since only a single IP Address is revealed in the attack on the server, there is a high probability that it is a Direct DoS SYN Flood Attack.

### Section 2: Explain how the attack is causing the website to malfunction

**When website visitors try to establish a connection with the web server, a three-way handshake occurs using the TCP protocol. Explain the three steps of the handshake:**

1. The client sends a SYN Packet to the server to request a connection.
2. The server responds with a SYN/ACK packet as acknowledgment of the communication.
3. The client receives the SYN/ACK packet and sends an ACK packet as acknowledgment of receipt. When this process is successful, the TCP connection is open and is in compliance to send and receive information.

**Explain what happens when a malicious actor sends a large number of SYN packets all at once:**

When a large number of SYN packets are sent, the server tries to respond to all of them with a SYN/ACK packet, leaving the port open. Since there is never an ACK response to finalize each request, the server becomes incapacitated, continuously receives new SYN packet requests, and sends timeout error messages because it cannot respond adequately.

**Explain what the logs indicate and how that affects the server:**

The logs show that initially the [SYN] request is successfully responded to, but progressively the attacker starts a process of flooding with SYN requests, and the server becomes unable to operate normally because it waits for the ACK response from the client, continues to receive new SYN packet requests, and cannot respond to all requests, sending timeout errors.

**Observations:** 
Attacks like these on the network cause service interruptions, rendering affected servers inoperable. They can lead to loss of clients or even the business itself, damage to reputation due to inability to maintain normal operation of activities and operations, and raise legal issues.

As forms of prevention against the attack, temporarily shutting down the server helps in recovering the machine to its normal operation, and configuring the firewall to block the IP address that was causing the SYN flood attack, although it may only be effective until the attacker can spoof another IP Address.

---
[Back to Cybersecurity Portfolio](README.md)
