# Projects

## Frequency Detector Design Project
For this project I built a circuit turned on a LED when a 25 kHz frequency was transmitted and blocked all other frequencys. To do this I built my circuit with 3 phases. 

1) A 2-Stage gain reductin sallen key filter, to filter out any frequency which wasn't 25 kHz. Each stage had a Q of 4 and a gain of 1 V/V.

        wο=25kHz convert new wο=25,000* π*2=157079.6 

              Q=4,   wο/Q=  157079.6/4=39269.9

        Formula=  ( wο/Q s)/(s^2+wο/Q s+〖wο〗^2 )=      39269.9s/(s^2+39269.9s+〖157079.6〗^2 )

                      Solve for A: Q=  1/(3-A)

                              4=1/(3-A)

                               3-A=1/4

                              -A=1/4-3

                              -A=-2.75=2.75

    Solve for R: wο=1/RC

                    157079.6=1/(R*(4.7*10^(-9)))

                    R(4.7*10^(-9) )=1/157079.6

            R=1/157079.6*1/(4.7*10^(-9) )=1354.5Ω

   Solve for 2R: 2R=2*1354.5=2709Ω

   Solve for (A-1)R: (2.75-1)*1354.5=2370.375Ω

   Calculate passband gain: K=AQ=2.75*4=11

Because the passband gain was too high I has to find a new K to caluclate for a reducted passband gain.

                          Knew=1

                        Knew=b*kold

                          1=b*11

                          b=1/11

Calculate new resistor values for a Sallen key with reduced gain:

                    R/b=1354.5/(1/11)=14899.5Ω

              R/((1-b))=1354.5/((1-1/11))=1489.95Ω

