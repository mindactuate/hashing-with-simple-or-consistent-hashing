# hashing-with-simple-or-consistent-hashing

Hi, I implemented a little tool to create shards with simple and consistent hashing.

As hashing algorithm I used [node-murmurhash](https://github.com/perezd/node-murmurhash#readme)

Its interesting to see, that

* simple hashing
  * offers a much more evenly distributed sharding
  * but needs much more resharding (movement of data between shards) when a shard is added or removed

* consistent hashing
  * needs few to no resharding when a shard is added or removed
  * but offers a worse distribution

Here you can find a codepen: [codepen.io/mindactuate/pen/OJBbYjr](https://codepen.io/mindactuate/pen/OJBbYjr)

Here a picture to visualize my findings:
- on the left side you see consistent hashing (left: 3 shards, right: 4 shards)
- on the right side you see simple hashing (left: 3 shards, right: 4 shards)
- the fields with the green background show if the specific field stays in the original shard when adding a 4th shard

![alt text](https://github.com/mindactuate/hashing-with-simple-or-consistent-hashing/blob/970c5a6012fd1e20a34d46e64a4dc3bf1f1892ea/picture_sharding.png)
