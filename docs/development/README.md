# Development

Install the `dev` extra for pytest, pytest-asyncio, Ruff, and mypy, then run the unit suite and
static checks from this repository:

```bash
python -m pip install -e ../orbit-workers
python -m pip install -e '.[dev]'
pytest
ruff check .
mypy
```

Contract tests must use deterministic model and protocol checks without provider credentials.
Provider sandbox acceptance belongs to each adapter and must be labeled separately from local unit
results. Keep public contracts provider-neutral and document any behavior that cannot be safely
normalized.

The current local unit matrix passes on CPython 3.11, 3.12, 3.13, and 3.14. This validates the
capability package's model and webhook-worker code paths; it does not verify a broker or payment
provider deployment.
