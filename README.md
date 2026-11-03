## Aegis Observer - 72-Hour Real Host Trial

This repository contains the time-locked, pre-compiled Aegis daemon and the necessary headers to integrate it with your AI agent.

### Step 1: Add Aegis to your AI Agent
Include the lightweight header in your agent's codebase to route telemetry to `/dev/shm`.

```cpp
#include "include/aegis.hpp"

int main() {
    // 1. Get a secure token for your agent
    uint64_t secure_token = register_agent_to_shared_memory();

    // 2. Push tool-call records directly to the shared memory
    push_to_ring_buffer(secure_token, ...);

    return 0;
}