# platform-health-monitor
Inspired by telemetry work.


CPU utilization
Temperature monitoring
Memory monitoring
PCIe monitoring
Alert generation
Dashboard


import psutil
import time

class TelemetryCollector:

    def collect(self):

        return {
            "cpu_percent":
                psutil.cpu_percent(),

            "memory_percent":
                psutil.virtual_memory().percent,

            "timestamp":
                time.time()
        }

collector = TelemetryCollector()

while True:

    print(
        collector.collect()
    )

    time.sleep(5)
