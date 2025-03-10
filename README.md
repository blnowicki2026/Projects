![image](https://github.com/user-attachments/assets/6befa854-adcc-4977-9042-c080f43e0365)# Projects

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

![image](https://github.com/user-attachments/assets/c0d4bdb1-707d-40c5-930f-d96ee8a09547)
MultiSim of my 2-stage reduced gain sallen key circuit

![image](https://github.com/user-attachments/assets/bd780d65-ccb7-4ba2-b386-052e74895414)
FRA of the peak detector working


2) The second phase was a peak detector to detect the peak of 25 kHz and would output 0V when 25 kHz wasn't detected.
   ![image](https://github.com/user-attachments/assets/57a6a3fc-b61c-44df-b8ff-ec4c3afe5aab)
   25 kHz detected

   ![image](https://github.com/user-attachments/assets/86d7e7e6-ed9e-493d-b6a5-cd6fe6fa0091)
   Both 10 kHz and 17 kHz are being transmitted, the peak detector outputs 0V

   
3) The third phase was a comparator which outputed 5V when the peak detector was outputing a voltage of 2V which caused the LED to light up

![image](https://github.com/user-attachments/assets/569e3f61-b73f-4451-bb5d-f85bd6860917)
Working ciruit detecting 25 kHz

