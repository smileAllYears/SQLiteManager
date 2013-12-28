SQLiteManager
=============

a sqlite thread safety tools in ios



#Usage
=============
like this

//insert data
    [mnger add:@[@[@"xiaoming",@21,@"北海"],@[@"huazai",@20,@"深圳"],@[@"xiaoxiao",@13,@"广州"]] condition:cdt back:^(SQLiteResult *res) {
            NSAssert(res.code==0, @"insert error");
            NSLog(@"%@",res);
    }];

//select
    [cdt clean];
    [mnger select:cdt back:^(SQLiteResult *res) {
        NSAssert(res.code==0, @"select error");
        NSLog(@"%@",res);
    }];
    
//update
    [cdt clean];
    [cdt fields:@[@"name",@"age"]];
    [mnger update:@[@"shagua",@111] condition:cdt back:^(SQLiteResult *res) {
        NSAssert(res.code==0, @"update error");
        NSLog(@"%@",res);
    }];

//delete
    [cdt clean];
    [cdt where:@"id = 3"];
    [mnger del:cdt back:^(SQLiteResult *res) {
        NSAssert(res.code==0, @"delete error");
        NSLog(@"%@",res);
    }];
