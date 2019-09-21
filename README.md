### annoy
---
https://github.com/spotify/annoy


```py
// test/hamming_index_test.py
import numpy
import random
from common import TestCase
from annoy import AnnoyIndex
from nose.plugins.skip import SkipTest

class HammingIndexTest(TestCase):
  def test_basic_conversion(self):
    f = 100
    i = AnnoyIndex(f, 'hamming')
    u = numpy.random.binomial(1, 0.5, f)
    v = numpy.random.binomial(1, 0.5, f)
    i.add_item(0, u)
    i.add_item(1, v)
    u2 = i.get_item_vector(0)
    v2 = i.get_item_vector(1)
    self.assertAlmostEqual(numpy.dot(u - u2, u - u2), 0.0)
    self.assertAlmostEqual(numpy.dot(v - v2, v - v2), 0.0)
    self.assertAlmostEqual(i.get_distance(0, 0), 0.0)
    self.assertAlmostEqual(i.get_distance(0, 1), 0.0)
    self.assertAlmostEqual(i.get_distance(0, 1), numpy.dot(u - v, u - v))
    self.assertAlmostEqual(i.get_distance(1, 0), numpy.dot(u - v, u - v))
  
  def test_basic_nns(self):
  
  def test_save_load(self):
  
  def test_many_vectors(self):
  
  @SkipTest
  def test_zero_vecotrs(self):
    bitstring = [
    ]
    vectors = [[int(bit) for bit in bitstring] for bitstring in bitstrings]
    
    f = 64
    idx = AnnoyIndex(f, 'humming')
    for i, v in enumerate(vectors):
      idx.add_item(i, v)
    
    idx.build(10)
    idx.save('idx.ann')
    idx = AnnoyIndex(f, 'hamming')
    idx.load('idx.ann')
    js, ds = idx.get_nns_by_item(0, 5, include_distances=True)
    self.assertEquals(js[0], 0)
    self.assertEquals(ds[:4], [0, 1, 1, 22])
```


```
```

```
```

