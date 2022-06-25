# A blog post on Observability 
- Source: OoenTelemetry Docs, Jaeger docs. 

# Current scenario of Microservices based applications dev

# Advantage and Challenges it has

# Fault Detection using :

# Tracing 

# Logs

# Telemetry

# Difference between the above concept 

# How does the observability as a system work

# How can observability help increasing efficiency :
- various back ends can be designed to make use of the trace logs and pinpoint errors and plan mitigation policies. 

# Current services available through cncf

#Future of Observablity, eBPF:
[How eBPF Streamlines the Service Mesh]()https://thenewstack.io/how-ebpf-streamlines-the-service-mesh/)

eBPF is a kernel technology that allows custom programs to run in the kernel. Those programs run in response to events, and there are thousands of possible events to which eBPF programs can be attached. These events include tracepoints, the entry to or exit from any function (in kernel or user space) or — importantly for service mesh — the arrival of network packets.

The eBPF-based Cilium project (which recently joined the Cloud Computing Foundation at Incubation level) brings this “sidecarless” model to the world of service mesh. As well as the conventional sidecar model, Cilium supports running a service mesh data plane using a single Envoy proxy instance per node. Using our example from earlier, this reduces the number of proxy instances from 100 to just three.

