    reporting-enabled = true
    bind-address = "127.0.0.1:8088"
    [[graphite]]
    enabled = true
   database = "graphite"
    retention-policy = ""
    bind-address = "127.0.0.1:2003"
    protocol = "tcp"
    consistency-level = "one"
   
   # Flush if this many points get buffered
    batch-size = 5000

   # number of batches that may be pending in memory
    batch-pending = 10

   # Flush at least this often even if we haven't hit buffer limit
    batch-timeout = "1s"

   ### This string joins multiple matching 'measurement' values providing more control over the final measurement name.
    separator = "."

    templates = [
    "fastnetmon.hosts.* app.measurement.cidr.direction.function.resource",
    "fastnetmon.networks.* app.measurement.cidr.direction.resource",
    "fastnetmon.total.* app.measurement.direction.resource"
