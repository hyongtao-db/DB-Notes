内容源自：https://www.modb.pro/db/599273


数据准备：
``` SQL
create table t1(a int, b int);
insert into t1 values(1,1);
-- 创建视图
create view vt1 as select * from t1;
-- 查询
select * from vt1;
```

查询重写后的结果：`select * from vt1;`
```
{QUERY 
:commandType 1 
:querySource 0 
:canSetTag true 
:utilityStmt <> 
:resultRelation 0 
:hasAggs false 
:hasWindowFuncs false 
:hasTargetSRFs false 
:hasSubLinks false 
:hasDistinctOn false 
:hasRecursive false 
:hasModifyingCTE false 
:hasForUpdate false 
:hasRowSecurity false 
:isReturn false 
:cteList <> 
:rtable (
    {RANGETBLENTRY 
    :alias <> 
    :eref 
        {ALIAS 
        :aliasname vt1 
        :colnames ("a" "b")
        }
    :rtekind 1 
    :subquery 
        {QUERY 
        :commandType 1 
        :querySource 0 
        :canSetTag true 
        :utilityStmt <> 
        :resultRelation 0 
        :hasAggs false 
        :hasWindowFuncs false 
        :hasTargetSRFs false 
        :hasSubLinks false 
        :hasDistinctOn false 
        :hasRecursive false 
        :hasModifyingCTE false 
        :hasForUpdate false 
        :hasRowSecurity false 
        :isReturn false 
        :cteList <> 
        :rtable (
        {RANGETBLENTRY 
        :alias <> 
        :eref 
            {ALIAS 
            :aliasname t1 
            :colnames ("a" "b")
            }
        :rtekind 0 
        :relid 16437 
        :relkind r 
        :rellockmode 1 
        :tablesample <> 
        :perminfoindex 1 
        :lateral false 
        :inh true 
        :inFromCl true 
        :securityQuals <>
        }
        )
        :rteperminfos (
        {RTEPERMISSIONINFO 
        :relid 16437 
        :inh true 
        :requiredPerms 2 
        :checkAsUser 10 
        :selectedCols (b 8 9)
        :insertedCols (b)
        :updatedCols (b)
        }
        )
        :jointree 
        {FROMEXPR 
        :fromlist (
            {RANGETBLREF 
            :rtindex 1
            }
        )
        :quals <>
        }
        :mergeActionList <> 
        :mergeUseOuterJoin false 
        :targetList (
        {TARGETENTRY 
        :expr 
            {VAR 
            :varno 1 
            :varattno 1 
            :vartype 23 
            :vartypmod -1 
            :varcollid 0 
            :varnullingrels (b)
            :varlevelsup 0 
            :varnosyn 1 
            :varattnosyn 1 
            :location -1
            }
        :resno 1 
        :resname a 
        :ressortgroupref 0 
        :resorigtbl 16437 
        :resorigcol 1 
        :resjunk false
        }
        {TARGETENTRY 
        :expr 
            {VAR 
            :varno 1 
            :varattno 2 
            :vartype 23 
            :vartypmod -1 
            :varcollid 0 
            :varnullingrels (b)
            :varlevelsup 0 
            :varnosyn 1 
            :varattnosyn 2 
            :location -1
            }
        :resno 2 
        :resname b 
        :ressortgroupref 0 
        :resorigtbl 16437 
        :resorigcol 2 
        :resjunk false
        }
        )
        :override 0 
        :onConflict <> 
        :returningList <> 
        :groupClause <> 
        :groupDistinct false 
        :groupingSets <> 
        :havingQual <> 
        :windowClause <> 
        :distinctClause <> 
        :sortClause <> 
        :limitOffset <> 
        :limitCount <> 
        :limitOption 0 
        :rowMarks <> 
        :setOperations <> 
        :constraintDeps <> 
        :withCheckOptions <> 
        :stmt_location -1 
        :stmt_len 35
        }
    :security_barrier false 
    :relid 16440 
    :relkind v 
    :rellockmode 1 
    :perminfoindex 1 
    :lateral false 
    :inh false 
    :inFromCl true 
    :securityQuals <>
    }
)
:rteperminfos (
    {RTEPERMISSIONINFO 
    :relid 16440 
    :inh true 
    :requiredPerms 2 
    :checkAsUser 0 
    :selectedCols (b 8 9)
    :insertedCols (b)
    :updatedCols (b)
    }
)
:jointree 
    {FROMEXPR 
    :fromlist (
        {RANGETBLREF 
        :rtindex 1
        }
    )
    :quals <>
    }
:mergeActionList <> 
:mergeUseOuterJoin false 
:targetList (
    {TARGETENTRY 
    :expr 
        {VAR 
        :varno 1 
        :varattno 1 
        :vartype 23 
        :vartypmod -1 
        :varcollid 0 
        :varnullingrels (b)
        :varlevelsup 0 
        :varnosyn 1 
        :varattnosyn 1 
        :location 7
        }
    :resno 1 
    :resname a 
    :ressortgroupref 0 
    :resorigtbl 16440 
    :resorigcol 1 
    :resjunk false
    }
    {TARGETENTRY 
    :expr 
        {VAR 
        :varno 1 
        :varattno 2 
        :vartype 23 
        :vartypmod -1 
        :varcollid 0 
        :varnullingrels (b)
        :varlevelsup 0 
        :varnosyn 1 
        :varattnosyn 2 
        :location 7
        }
    :resno 2 
    :resname b 
    :ressortgroupref 0 
    :resorigtbl 16440 
    :resorigcol 2 
    :resjunk false
    }
)
:override 0 
:onConflict <> 
:returningList <> 
:groupClause <> 
:groupDistinct false 
:groupingSets <> 
:havingQual <> 
:windowClause <> 
:distinctClause <> 
:sortClause <> 
:limitOffset <> 
:limitCount <> 
:limitOption 0 
:rowMarks <> 
:setOperations <> 
:constraintDeps <> 
:withCheckOptions <> 
:stmt_location 0 
:stmt_len 17
}
```
