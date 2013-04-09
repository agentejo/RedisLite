RedisLite
=========

A simple storage class inspired by the redis api on top of Sqlite.

# Usage

    $db = new RedisLite("PATH_TO_WRITABLE_FOLDER/mydb");

    $db->set("mykey", 1);
    
    $db->incr("mykey");
    
    $db->get("mykey"); // 2

    // Lists

    db->rpush("mylist", "item1");
    db->rpush("mylist", "item2");
    $db->lpush("mylist", "item3");

    $db->get("mylist");  // ["item3", "item1", "item2"]

    // hashes

    $db->hset("myhash", "myfield", 1);
    $db->hmset("myhash", "myfield-1", "value-1", "myfield-2", "value-2");

    $db->hkeys("myhash"); // ["myfield", "myfield-1", "myfield-2"]
    $db->hvals("myhash"); // [1, "value-1", "value-2"]

    $db->hget("myhash", "myfield"); // 1

    $db->get("myhash"); // array("myfield"=>1, "myfield-1"=>"value-1", "myfield-2"=>"value-2")

## implemented methods

    set, get, exists, del, type, incr, decr, 
    llen, lpush, rpush, lset, lindex,
    hset, hget, hgetall, hexists, hkeys, hvals, hlen, hincrby, hmset, hmget
    