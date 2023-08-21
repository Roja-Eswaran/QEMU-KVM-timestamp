# Vanilla_QEMU_4.1.0_UDP_Timestamp
 
 The current QEMU/KVM code measures the start and end timestamp for migration at the source which is inaccurate. In order to accurately measure the total migration time and downtime in QEMU for live migration, we have employed a more precise method instead of solely relying on the source QEMU's measurement. Specifically, we send UDP packets to a third, separate measurement node at the start and end of migration and downtime. The measurement node records the arrival times of these packets using the \textit{tcpdump} tool, and the difference in these arrival times represents the total migration time or downtime. This method provides more accurate timings, as the dedicated measurement node has a better view of the end-to-end live migration procedure.


