Coiled Cloud Issues
===================

Thank you for trying out Coiled Cloud.

We are currently in a very experimental stage,
and so we appreciate your willingness to experiment with us and report issues.

We can't promise that everything will work, but we can promise to be responsive.

Start
-----

To get started, download the Python client library, connect to your account, and create a cluster:

### Download Python Client Library from PyPI

```
pip install coiled-cloud
```

### Connect to your account

```python
from coiled_cloud import Cloud, Cluster
from getpass import getpass

cloud = Cloud(user="your-username", password=getpass("Password: "))
```

### Create a Dask cluster on the cloud

```python
cluster = Cluster()
```

### Connect with Dask and do work

```python
import dask
from dask.distributed import Client

client = Client(cluster)

df = dask.datasets.timeseries()
df.groupby("name").x.std().compute()
```

### Optionally look at the dashboard

```python
>>> client.dashboard_link
https://ecs...
```
