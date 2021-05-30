like systemd for an individual app

names:
- applead?
- programd?

building blocks:
- units (modules?)
  - provide features
  - may conflict with other units/features
- targets

subsystems:
- config
- logging
- multiprocessing/threading/asyncio

# Targets
examples:
- prod
- test
- gen docs from source code (by running this code, not static analysis!)

I think units/features will contain stages bound to different targets. \[Well, already looks very complex.]
