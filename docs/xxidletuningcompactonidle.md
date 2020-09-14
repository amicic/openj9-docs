<!--
* Copyright (c) 2017, 2020 IBM Corp. and others
*
* This program and the accompanying materials are made
* available under the terms of the Eclipse Public License 2.0
* which accompanies this distribution and is available at
* https://www.eclipse.org/legal/epl-2.0/ or the Apache
* License, Version 2.0 which accompanies this distribution and
* is available at https://www.apache.org/licenses/LICENSE-2.0.
*
* This Source Code may also be made available under the
* following Secondary Licenses when the conditions for such
* availability set forth in the Eclipse Public License, v. 2.0
* are satisfied: GNU General Public License, version 2 with
* the GNU Classpath Exception [1] and GNU General Public
* License, version 2 with the OpenJDK Assembly Exception [2].
*
* [1] https://www.gnu.org/software/classpath/license.html
* [2] http://openjdk.java.net/legal/assembly-exception.html
*
* SPDX-License-Identifier: EPL-2.0 OR Apache-2.0 OR GPL-2.0 WITH
* Classpath-exception-2.0 OR LicenseRef-GPL-2.0 WITH Assembly-exception
-->

# -XX:\[+|-\]IdleTuningCompactOnIdle

**(Linux&reg; only)**

This option controls garbage collection processing with compaction when the state of the OpenJ9 VM is set to idle.

<i class="fa fa-exclamation-triangle" aria-hidden="true"></i> **Restrictions:**
  
1. This option was deprecated in release 0.15.0 and will be removed in the future.
2. This option applies only to Linux&reg; architectures when the Generational Concurrent (`gencon`) garbage collection policy is in use.
3. This option is not effective if the object heap is configured to use large pages.
4. This option is not effective if [XX:+IdleTuningGcOnIdle](xxidletuninggconidle.md) is not specified.

## Syntax

        -XX:[+|-]IdleTuningCompactOnIdle

Forces Heap compaction during Global GC when entering idle state. As of release 0.15, compaction is triggered by internal heuristics that look into the amount of fragmented pages and typically there is no need to force compaction. For releases 0.15-0.22, compaction would still be forced, if VM was running in container environment.

The `-XX:+IdleTuningCompactOnIdle` option can be used with the `-XX:+IdleTuningMinIdleWaitTime`, which controls the amount of time that the VM must be idle before an idle state is set. If a value for the `-XX:+IdleTuningMinIdleWaitTime` option is not explicitly specified, the VM sets a default value of 180 seconds.

## See also

- [-XX:IdleTuningMinFreeHeapOnIdle](xxidletuningminfreeheaponidle.md)
- [-XX:IdleTuningMinIdleWaitTime](xxidletuningminidlewaittime.md)
- [-XX:\[+|-\]IdleTuningGcOnIdle](xxidletuninggconidle.md)



<!-- ==== END OF TOPIC ==== xxidletuningcompactonidle.md ==== -->
