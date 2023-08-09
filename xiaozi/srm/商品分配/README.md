## 商品分配

!> 商品分配时需要严格按照顺序写入NC数据库表

!> 中台商品核算单位信息表中需要保存NC**商品管理档案ID**及**物料生产档案ID**

1. 插入商品管理档案，表名`BD_INVMANDOC`；
2. 插入物料生产档案，表名`BD_PRODUCE`；

?> 字段描述中赋值方式为`固定值`且值为`[NULL]`的字段，`insert`时可忽略

### 商品管理档案

#### 字段描述

| 字段名称                     | 字段列名               | 赋值方式 | 值                                                           | 示例                 |
| :--------------------------- | :--------------------- | :------: | :----------------------------------------------------------- | :------------------- |
| ABC分类                      | ABCTYPE                |  固定值  | A                                                            | A                    |
| 是否辅币核算成本             | ACCFLAG                |  固定值  | N                                                            | N                    |
| 助记码                       | CINVMNECODE            |  固定值  | [NULL]                                                       | [NULL]               |
| 是否根据消耗结算             | CONSUMESETTLEFLAG      |  固定值  | N                                                            | N                    |
| 合作期限从                   | COOPDAYFROM            |  固定值  | [NULL]                                                       | [NULL]               |
| 合作期限到                   | COOPDAYTO              |  固定值  | [NULL]                                                       | [NULL]               |
| 参考成本                     | COSTPRICE              |  固定值  | [NULL]                                                       | [NULL]               |
| 创建时间                     | CREATETIME             |   变量   | 当前时间                                                     | 2023-06-19 15:41:53  |
| 创建人                       | CREATOR                |   变量   | 当前操作人员对应NC员工ID                                     | 0001K81000000000E2YQ |
| 自定义项1                    | DEF1                   |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项10                   | DEF10                  |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项11                   | DEF11                  |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项12                   | DEF12                  |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项13                   | DEF13                  |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项14                   | DEF14                  |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项15                   | DEF15                  |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项16                   | DEF16                  |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项17                   | DEF17                  |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项18                   | DEF18                  |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项19                   | DEF19                  |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项2                    | DEF2                   |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项20                   | DEF20                  |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项3                    | DEF3                   |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项4                    | DEF4                   |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项5                    | DEF5                   |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项6                    | DEF6                   |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项7                    | DEF7                   |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项8                    | DEF8                   |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项9                    | DEF9                   |  固定值  | [NULL]                                                       | [NULL]               |
| 删除标志                     | DR                     |  固定值  | 0                                                            | 0                    |
| 出口退税率                   | EXPAYBACKTAX           |  固定值  | 0                                                            | 0                    |
| 自由项1                      | FREE1                  |  固定值  | [NULL]                                                       | [NULL]               |
| 自由项2                      | FREE2                  |  固定值  | [NULL]                                                       | [NULL]               |
| 自由项3                      | FREE3                  |  固定值  | [NULL]                                                       | [NULL]               |
| 自由项4                      | FREE4                  |  固定值  | [NULL]                                                       | [NULL]               |
| 自由项5                      | FREE5                  |  固定值  | [NULL]                                                       | [NULL]               |
| 等级                         | GRADE                  |  固定值  | [NULL]                                                       | [NULL]               |
| 存货生命周期                 | INVLIFEPERIOD          |  固定值  | 0                                                            | 0                    |
| 附属品                       | ISAPPENDANT            |  固定值  | Y                                                            | Y                    |
| 是否自动进行订单ATP检查      | ISAUTOATPCHECK         |  固定值  | Y                                                            | Y                    |
| 是否可计算存货成本           | ISCANCALCULATEDINVCOST |  固定值  | Y                                                            | Y                    |
| 是否可进行采购               | ISCANPURCHASED         |  固定值  | Y                                                            | Y                    |
| 是否可销售开票               | ISCANSALEINVOICE       |  固定值  | Y                                                            | Y                    |
| 是否可进行销售               | ISCANSOLD              |  固定值  | Y                                                            | Y                    |
| 是否可配置                   | ISCONFIGABLE           |  固定值  | N                                                            | N                    |
| 是否控制物料生产档案的计划价 | ISCTLPRODPLANPRICE     |  固定值  | N                                                            | N                    |
| 是否BOM父项                  | ISFATHEROFBOM          |  固定值  | N                                                            | N                    |
| 销售退货是否免检             | ISINVRETFREEOFCHK      |  固定值  | Y                                                            | Y                    |
| 销售退货是否根据检验结果入库 | ISINVRETINSTOBYCHK     |   变量   | 根据**退货根据检验结果入库**字段值进行赋值，默认N            | N                    |
| 存货是否可退换               | ISINVRETURNED          |  固定值  | Y                                                            | Y                    |
| 否允许无合同采购             | ISNOCONALLOWED         |  固定值  | Y                                                            | Y                    |
| 是否主条码管理               | ISPRIMARYBARCODE       |  固定值  | N                                                            | N                    |
| 定期检验                     | ISRECURRENTCHECK       |  固定值  | N                                                            | N                    |
| 是否需求管理                 | ISSALABLE              |  固定值  | N                                                            | N                    |
| 是否次条码管理               | ISSECONDARYBARCODE     |  固定值  | N                                                            | N                    |
| 是否采购自核准供应商         | ISSELFAPPRSUPPLIER     |  固定值  | Y                                                            | Y                    |
| 是否特征项                   | ISSPECIALTY            |  固定值  | N                                                            | N                    |
| 是否按供应商现存             | ISSUPPLIERSTOCK        |  固定值  | N                                                            | N                    |
| 是否可作出入库               | ISUSED                 |  固定值  | Y                                                            | Y                    |
| 是否虚项                     | ISVIRTUAL              |  固定值  | N                                                            | N                    |
| 保管损耗率                   | KEEPWASTERATE          |  固定值  | 0                                                            | 0                    |
| 最低售价                     | LOWESTPRICE            |  固定值  | 0                                                            | 0                    |
| 税目                         | MANTAXITEM             |  固定值  | [NULL]                                                       | [NULL]               |
| 最高限价                     | MAXPRICE               |  固定值  | 0                                                            | 0                    |
| 备注                         | MEMO                   |  固定值  | [NULL]                                                       | [NULL]               |
| 修改人                       | MODIFIER               |   变量   | 新增时为NULL，修改时赋值                                     | [NULL]               |
| 修改时间                     | MODIFYTIME             |   变量   | 新增时为NULL，修改时赋值                                     | [NULL]               |
| 是否允许负库存               | NEGALLOWED             |  固定值  | N                                                            | N                    |
| 出库优先级                   | OUTPRIORITY            |  固定值  | 0                                                            | 0                    |
| 是否出库跟踪入库             | OUTTRACKIN             |  固定值  | N                                                            | N                    |
| 配额开始                     | PEBEGIN                |  固定值  | [NULL]                                                       | [NULL]               |
| 配额结束                     | PEEND                  |  固定值  | [NULL]                                                       | [NULL]               |
| 公司主键                     | PK_CORP                |   变量   | 核算单位对应NC的ID                                           | 1005                 |
| 主供应商                     | PK_CUMANDOC            |  固定值  | [NULL]                                                       | [NULL]               |
| 默认工厂                     | PK_DFTFACTORY          |  固定值  | [NULL]                                                       | [NULL]               |
| 存货档案主键                 | PK_INVBASDOC           |   变量   | 商品对应NC存货档案的ID                                       | 0001H9100000000FSPWT |
| 存货管理档案主键             | PK_INVMANDOC           |   变量   | 该表主键，自动生成唯一值                                     | 0001H9100000000FSPWY |
| 封存人                       | PK_SEALUSER            |  固定值  | [NULL]                                                       | [NULL]               |
| 计划价                       | PLANPRICE              |  固定值  | [NULL]                                                       | [NULL]               |
| 产地                         | PRODAREA               |  固定值  | [NULL]                                                       | [NULL]               |
| 采购策略                     | PURCHASESTGE           |  固定值  | 0                                                            | 0                    |
| 采购损耗率                   | PURWASTERATE           |  固定值  | 0                                                            | 0                    |
| 保质期                       | QUALITYDAYNUM          |   变量   | 取值为保质期值，默认为2                                      | 2                    |
| 是否保质期管理               | QUALITYMANFLAG         |   变量   | 保质期单位为”无保质期“时为N，否则Y； 医疗件默认Y，非医疗件默认N | Y                    |
| 保质期单位                   | QUALITYPERIODUNIT      |   变量   | 根据选择的单位赋值，默认0 0,年 1,月                          | 0                    |
| 定期检验周期                 | RECURRENTCHKCYC        |  固定值  | [NULL]                                                       | [NULL]               |
| 参考售价                     | REFSALEPRICE           |  固定值  | [NULL]                                                       | [NULL]               |
| 封存时间                     | SEALDATE               |  固定值  | [NULL]                                                       | [NULL]               |
| 封存标志                     | SEALFLAG               |  固定值  | N                                                            | N                    |
| 是否受托代销                 | SELLPROXYFLAG          |  固定值  | N                                                            | N                    |
| 是否进行序列号管理           | SERIALMANAFLAG         |  固定值  | N                                                            | N                    |
| 时间戳                       | TS                     |   变量   | 当前时间                                                     | 2023-06-19 15:41:53  |
| 是否批次管理                 | WHOLEMANAFLAG          |  固定值  | Y                                                            | Y                    |

#### SQL示例

```sql
/*商品管理档案*/
INSERT INTO
    BD_INVMANDOC (
        ABCTYPE,
        ACCFLAG,
        CINVMNECODE,
        CONSUMESETTLEFLAG,
        COOPDAYFROM,
        COOPDAYTO,
        COSTPRICE,
        CREATETIME,
        CREATOR,
        DEF1,
        DEF10,
        DEF11,
        DEF12,
        DEF13,
        DEF14,
        DEF15,
        DEF16,
        DEF17,
        DEF18,
        DEF19,
        DEF2,
        DEF20,
        DEF3,
        DEF4,
        DEF5,
        DEF6,
        DEF7,
        DEF8,
        DEF9,
        DR,
        EXPAYBACKTAX,
        FREE1,
        FREE2,
        FREE3,
        FREE4,
        FREE5,
        GRADE,
        INVLIFEPERIOD,
        ISAPPENDANT,
        ISAUTOATPCHECK,
        ISCANCALCULATEDINVCOST,
        ISCANPURCHASED,
        ISCANSALEINVOICE,
        ISCANSOLD,
        ISCONFIGABLE,
        ISCTLPRODPLANPRICE,
        ISFATHEROFBOM,
        ISINVRETFREEOFCHK,
        ISINVRETINSTOBYCHK,
        ISINVRETURNED,
        ISNOCONALLOWED,
        ISPRIMARYBARCODE,
        ISRECURRENTCHECK,
        ISSALABLE,
        ISSECONDARYBARCODE,
        ISSELFAPPRSUPPLIER,
        ISSPECIALTY,
        ISSUPPLIERSTOCK,
        ISUSED,
        ISVIRTUAL,
        KEEPWASTERATE,
        LOWESTPRICE,
        MANTAXITEM,
        MAXPRICE,
        MEMO,
        MODIFIER,
        MODIFYTIME,
        NEGALLOWED,
        OUTPRIORITY,
        OUTTRACKIN,
        PEBEGIN,
        PEEND,
        PK_CORP,
        PK_CUMANDOC,
        PK_DFTFACTORY,
        PK_INVBASDOC,
        PK_INVMANDOC,
        PK_SEALUSER,
        PLANPRICE,
        PRODAREA,
        PURCHASESTGE,
        PURWASTERATE,
        QUALITYDAYNUM,
        QUALITYMANFLAG,
        QUALITYPERIODUNIT,
        RECURRENTCHKCYC,
        REFSALEPRICE,
        SEALDATE,
        SEALFLAG,
        SELLPROXYFLAG,
        SERIALMANAFLAG,
        TS,
        WHOLEMANAFLAG
    )
VALUES
    (
        'A',
        'N',
        NULL,
        'N',
        NULL,
        NULL,
        NULL,
        '2023-06-19 15:41:53',
        '0001K81000000000E2YQ',
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        'Y',
        'Y',
        'Y',
        'Y',
        'Y',
        'Y',
        'N',
        'N',
        'N',
        'Y',
        'N',
        'Y',
        'Y',
        'N',
        'N',
        'N',
        'N',
        'Y',
        'N',
        'N',
        'Y',
        'N',
        0,
        0,
        NULL,
        0,
        NULL,
        NULL,
        NULL,
        'N',
        0,
        'N',
        NULL,
        NULL,
        '1005',
        NULL,
        NULL,
        '0001H9100000000FSPWT',
        '0001H9100000000FSPWY',
        NULL,
        NULL,
        NULL,
        '0',
        0,
        NULL,
        'N',
        2,
        NULL,
        NULL,
        NULL,
        'N',
        'N',
        'N',
        '2023-06-19 15:41:53',
        'Y'
    );
```



---

### 物料生产档案

#### 字段描述

| 字段名称                         | 字段列名               | 赋值方式 | 值                                                           | 示例                 |
| :------------------------------- | :--------------------- | :------: | :----------------------------------------------------------- | :------------------- |
| ABC分类1                         | ABCFL                  |  固定值  | A                                                            | A                    |
| ABC分类库存资金占用角度          | ABCFUNDEG              |  固定值  | C                                                            | C                    |
| ABC分类毛利角度                  | ABCGROSSPFT            |  固定值  | C                                                            | C                    |
| ABC分类采购额角度                | ABCPURCHASE            |  固定值  | C                                                            | C                    |
| ABC分类销售额角度                | ABSSALES               |  固定值  | C                                                            | C                    |
| 需求时界                         | ACCQUIRETIME           |  固定值  | [NULL]                                                       | [NULL]               |
| 提前期批量                       | AHEADBATCH             |  固定值  | [NULL]                                                       | [NULL]               |
| 提前期系数                       | AHEADCOFF              |  固定值  | [NULL]                                                       | [NULL]               |
| 批量增量                         | BATCHINCRNUM           |  固定值  | [NULL]                                                       | [NULL]               |
| 批量数量                         | BATCHNUM               |  固定值  | [NULL]                                                       | [NULL]               |
| 批量周期                         | BATCHPERIODNUM         |  固定值  | [NULL]                                                       | [NULL]               |
| 批量规则                         | BATCHRULE              |  固定值  | ZJ                                                           | ZJ                   |
| 备料固定实测折扣系数             | BLGDSCZKXS             |  固定值  | [NULL]                                                       | [NULL]               |
| BOM类型                          | BOMTYPE                |  固定值  | 0                                                            | 0                    |
| 采购组织                         | CGZZ                   |  固定值  | [NULL]                                                       | [NULL]               |
| 是否免检                         | CHKFREEFLAG            |   变量   | 取值为表单中的**是否免检**字段，默认N                        | N                    |
| 转库批量                         | CHNGAMOUNT             |  固定值  | [NULL]                                                       | [NULL]               |
| 参考成本                         | CKCB                   |  固定值  | [NULL]                                                       | [NULL]               |
| 参考售价                         | CKSJ                   |  固定值  | [NULL]                                                       | [NULL]               |
| 是否需求合并                     | COMBINEFLAG            |  固定值  | N                                                            | N                    |
| 确认时界                         | CONFIRMTIME            |  固定值  | [NULL]                                                       | [NULL]               |
| 倒冲标志                         | CONVERSEFLAG           |  固定值  | N                                                            | N                    |
| 创建时间                         | CREATETIME             |   变量   | 当前时间                                                     | 2023-06-19 15:42:13  |
| 创建人                           | CREATOR                |   变量   | 当前操作人员对应NC员工ID                                     | 0001K81000000000E2YQ |
| 现存量                           | CURRENTAMOUNT          |  固定值  | [NULL]                                                       | [NULL]               |
| 发料基准量                       | DATUMOFSEND            |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项1                        | DEF1                   |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项2                        | DEF2                   |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项3                        | DEF3                   |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项4                        | DEF4                   |  固定值  | [NULL]                                                       | [NULL]               |
| 自定义项5                        | DEF5                   |  固定值  | [NULL]                                                       | [NULL]               |
| 删除标志                         | DR                     |  固定值  | 0                                                            | 0                    |
| 经济批量                         | ECOBATCH               |  固定值  | [NULL]                                                       | [NULL]               |
| 后段提前期                       | ENDAHEAD               |  固定值  | [NULL]                                                       | [NULL]               |
| 副产品产量估算方案               | FCPCLGSFA              |  固定值  | 0                                                            | 0                    |
| 副供应商                         | FGYS                   |  固定值  | [NULL]                                                       | [NULL]               |
| 固定提前期                       | FIXEDAHEAD             |  固定值  | [NULL]                                                       | [NULL]               |
| 固定周期起始日                   | FIXPERIODBEGIN         |  固定值  | [NULL]                                                       | [NULL]               |
| 坯料长度                         | FLANLENNUM             |  固定值  | [NULL]                                                       | [NULL]               |
| 坯料制件数                       | FLANMADENUM            |  固定值  | [NULL]                                                       | [NULL]               |
| 坯料宽度                         | FLANWIDENUM            |  固定值  | [NULL]                                                       | [NULL]               |
| 供方物料编码                     | GFWLBM                 |  固定值  | [NULL]                                                       | [NULL]               |
| 毛重量                           | GROSSWTNUM             |  固定值  | [NULL]                                                       | [NULL]               |
| 是否可计算存货成本               | ISCANCALCULATEDINVCOST |  固定值  | [NULL]                                                       | [NULL]               |
| 是否按生产订单核算成本           | ISCOSTBYORDER          |  固定值  | N                                                            | N                    |
| 是否生成子生产订单               | ISCREATESONPRODORDER   |  固定值  | N                                                            | N                    |
| 是否受固定周期约束               | ISCTLBYFIXPERIOD       |  固定值  | N                                                            | N                    |
| 是否主条码管理                   | ISCTLBYPRIMARYCODE     |  固定值  | N                                                            | N                    |
| 是否次条码管理                   | ISCTLBYSECONDARYCODE   |  固定值  | N                                                            | N                    |
| 是否成本输出                     | ISCTOUTPUT             |  固定值  | Y                                                            | Y                    |
| 是否成分报检                     | ISELEMENTCHECK         |  固定值  | N                                                            | N                    |
| 是否BOM父项                      | ISFATHEROFBOM          |  固定值  | [NULL]                                                       | [NULL]               |
| 是否分项结转                     | ISFXJZ                 |  固定值  | N                                                            | N                    |
| 是否发料                         | ISSEND                 |  固定值  | Y                                                            | Y                    |
| 是否按基准量发料                 | ISSENDBYDATUM          |  固定值  | N                                                            | N                    |
| 是否可出入库                     | ISUSED                 |  固定值  | Y                                                            | Y                    |
| 是否应用路线                     | ISUSEROUTE             |  固定值  | N                                                            | N                    |
| 是否成套发料                     | ISWHOLESETSEND         |  固定值  | Y                                                            | Y                    |
| 计划价                           | JHJ                    |  固定值  | [NULL]                                                       | [NULL]               |
| 检验如何指导业务                 | JYRHZDYW               |  固定值  | 0                                                            | 0                    |
| 低层码                           | LOWLEVELCODE           |  固定值  | 0                                                            | 0                    |
| 最低库存                         | LOWSTOCKNUM            |  固定值  | [NULL]                                                       | [NULL]               |
| 物料分类                         | MATERCLASS             |  固定值  | 0                                                            | 0                    |
| 物料形态                         | MATERSTATE             |  固定值  | 2                                                            | 2                    |
| 物料类型                         | MATERTYPE              |  固定值  | MR                                                           | MR                   |
| 最高库存                         | MAXSTORNUM             |  固定值  | [NULL]                                                       | [NULL]               |
| 最小批量                         | MINBATCHNUM            |  固定值  | [NULL]                                                       | [NULL]               |
| 最小乘数                         | MINMULNUM              |  固定值  | 1                                                            | 1                    |
| 修改人                           | MODIFIER               |   变量   | 新增时为NULL，修改时赋值                                     | [NULL]               |
| 修改时间                         | MODIFYTIME             |   变量   | 新增时为NULL，修改时赋值                                     | [NULL]               |
| 内部转移价                       | NBZYJ                  |  固定值  | [NULL]                                                       | [NULL]               |
| 净重量                           | NETWTNUM               |  固定值  | [NULL]                                                       | [NULL]               |
| 能源折标煤系数                   | NYZBMXS                |  固定值  | [NULL]                                                       | [NULL]               |
| 日均出库量历史天数               | OUTNUMHISTORYDAYS      |  固定值  | [NULL]                                                       | [NULL]               |
| 委外类型                         | OUTTYPE                |  固定值  | OA                                                           | OA                   |
| 批次号生产生成点                 | PCHSCSCD               |  固定值  | 0                                                            | 0                    |
| 库存组织主键                     | PK_CALBODY             |   变量   | 根据核算单位查询NC对应库存组织主键 <br />`SELECT PK_CALBODY FROM BD_CALBODY WHERE PK_CORP = '$NCid$';` | 1005K81000000000099E |
| 出库计量秤                       | PK_CKJLCID             |  固定值  | [NULL]                                                       | [NULL]               |
| 公司主键                         | PK_CORP                |   变量   | 核算单位对应NC的ID                                           | 1005                 |
| 分管生产部门                     | PK_DEPTDOC3            |  固定值  | [NULL]                                                       | [NULL]               |
| 存货基本档案主键                 | PK_INVBASDOC           |   变量   | 商品对应NC存货档案的ID                                       | 0001H9100000000FSPX0 |
| 存货管理档案主键                 | PK_INVMANDOC           |   变量   | **步骤1中插入的表记录主键**                                  | 1005H91000000012PGW3 |
| 存货管理档案生产页主键           | PK_PRODUCE             |   变量   | 该表主键，自动生成唯一值                                     | 0001H9100000000FSPX2 |
| 分管生产业务员                   | PK_PSNDOC3             |  固定值  | [NULL]                                                       | [NULL]               |
| 物料计划员                       | PK_PSNDOC4             |  固定值  | [NULL]                                                       | [NULL]               |
| 入库计量秤                       | PK_RKJLCID             |  固定值  | [NULL]                                                       | [NULL]               |
| 封存人                           | PK_SEALUSER            |  固定值  | [NULL]                                                       | [NULL]               |
| 主仓库                           | PK_STORDOC             |  固定值  | [NULL]                                                       | [NULL]               |
| 前段提前期                       | PREVAHEAD              |  固定值  | [NULL]                                                       | [NULL]               |
| 记价方式                         | PRICEMETHOD            |  固定值  | 3                                                            | 3                    |
| 是否关键件                       | PRIMARYFLAG            |  固定值  | N                                                            | N                    |
| 最大周转天数                     | PRIMNESSNUM            |  固定值  | [NULL]                                                       | [NULL]               |
| 生产方式                         | PRODUCEMETHOD          |  固定值  | 0                                                            | 0                    |
| 定额重量                         | RATIONWTNUM            |  固定值  | 0.5                                                          | 0.5                  |
| 存货可用量，真正表示可用量的多少 | REALUSABLEAMOUNT       |  固定值  | [NULL]                                                       | [NULL]               |
| 工艺路线类型                     | ROADTYPE               |  固定值  | 0                                                            | 0                    |
| 舍入值                           | ROUNDINGNUM            |  固定值  | 0.5                                                          | 0.5                  |
| 安全库存                         | SAFETYSTOCKNUM         |  固定值  | [NULL]                                                       | [NULL]               |
| 计划属性                         | SCHEATTR               |  固定值  | [NULL]                                                       | [NULL]               |
| 生产批量                         | SCPL                   |  固定值  | [NULL]                                                       | [NULL]               |
| 生成生产订单模式                 | SCSCDDMS               |  固定值  | 0                                                            | 0                    |
| 实测小于标准是否折扣             | SCXYBZSFZK             |  固定值  | N                                                            | N                    |
| 封存日期                         | SEALDATE               |  固定值  | [NULL]                                                       | [NULL]               |
| 封存标志                         | SEALFLAG               |  固定值  | N                                                            | N                    |
| 是否部件                         | SFBJ                   |  固定值  | [NULL]                                                       | [NULL]               |
| 是否成本对象                     | SFCBDX                 |  固定值  | N                                                            | N                    |
| 是否辅助服务                     | SFFZFW                 |  固定值  | N                                                            | N                    |
| 是否批次核算                     | SFPCHS                 |  固定值  | Y                                                            | Y                    |
| 是否生产线生产                   | SFSCX                  |  固定值  | [NULL]                                                       | [NULL]               |
| 是否折标                         | SFZB                   |  固定值  | N                                                            | N                    |
| 是否最终产品                     | SFZZCP                 |  固定值  | N                                                            | N                    |
| 是否必须依据检验结果入库         | STOCKBYCHECK           |  固定值  | N                                                            | N                    |
| 库存下限天数                     | STOCKLOWERDAYS         |  固定值  | [NULL]                                                       | [NULL]               |
| 库存上限天数                     | STOCKUPPERDAYS         |  固定值  | [NULL]                                                       | [NULL]               |
| 累计提前期                       | SUMAHEAD               |  固定值  | [NULL]                                                       | [NULL]               |
| 供应类型                         | SUPPLYTYPE             |  固定值  | 0                                                            | 0                    |
| 时间戳                           | TS                     |   变量   | 当前时间                                                     | 2023-06-19 15:42:13  |
| 存货可用量计算方案字符串         | USABLEAMOUNT           |  固定值  | 1111111111111011                                             | 1111111111111011     |
| 可用量是否按自由项计算           | USABLEAMOUNTBYFREE     |  固定值  | NNN                                                          | NNN                  |
| 是否虚项                         | VIRTUALFLAG            |  固定值  | N                                                            | N                    |
| 废品系数                         | WASTERRATE             |  固定值  | [NULL]                                                       | [NULL]               |
| 完工固定实测折扣系数             | WGGDSCZKXS             |  固定值  | [NULL]                                                       | [NULL]               |
| 完工后续处理                     | WGHXCL                 |  固定值  | 0                                                            | 0                    |
| 预备供应商                       | YBGYS                  |  固定值  | [NULL]                                                       | [NULL]               |
| 折标参照检验项目                 | ZBCZJYXM               |  固定值  | [NULL]                                                       | [NULL]               |
| 折标系数                         | ZBXS                   |  固定值  | [NULL]                                                       | [NULL]               |
| 再定货点                         | ZDHD                   |  固定值  | [NULL]                                                       | [NULL]               |
| 主供应商                         | ZGYS                   |  固定值  | [NULL]                                                       | [NULL]               |


#### SQL示例

```sql
/*物料生产档案*/
INSERT INTO
    BD_PRODUCE (
        ABCFL,
        ABCFUNDEG,
        ABCGROSSPFT,
        ABCPURCHASE,
        ABSSALES,
        ACCQUIRETIME,
        AHEADBATCH,
        AHEADCOFF,
        BATCHINCRNUM,
        BATCHNUM,
        BATCHPERIODNUM,
        BATCHRULE,
        BLGDSCZKXS,
        BOMTYPE,
        CGZZ,
        CHKFREEFLAG,
        CHNGAMOUNT,
        CKCB,
        CKSJ,
        COMBINEFLAG,
        CONFIRMTIME,
        CONVERSEFLAG,
        CREATETIME,
        CREATOR,
        CURRENTAMOUNT,
        DATUMOFSEND,
        DEF1,
        DEF2,
        DEF3,
        DEF4,
        DEF5,
        DR,
        ECOBATCH,
        ENDAHEAD,
        FCPCLGSFA,
        FGYS,
        FIXEDAHEAD,
        FIXPERIODBEGIN,
        FLANLENNUM,
        FLANMADENUM,
        FLANWIDENUM,
        GFWLBM,
        GROSSWTNUM,
        ISCANCALCULATEDINVCOST,
        ISCOSTBYORDER,
        ISCREATESONPRODORDER,
        ISCTLBYFIXPERIOD,
        ISCTLBYPRIMARYCODE,
        ISCTLBYSECONDARYCODE,
        ISCTOUTPUT,
        ISELEMENTCHECK,
        ISFATHEROFBOM,
        ISFXJZ,
        ISSEND,
        ISSENDBYDATUM,
        ISUSED,
        ISUSEROUTE,
        ISWHOLESETSEND,
        JHJ,
        JYRHZDYW,
        LOWLEVELCODE,
        LOWSTOCKNUM,
        MATERCLASS,
        MATERSTATE,
        MATERTYPE,
        MAXSTORNUM,
        MINBATCHNUM,
        MINMULNUM,
        MODIFIER,
        MODIFYTIME,
        NBZYJ,
        NETWTNUM,
        NYZBMXS,
        OUTNUMHISTORYDAYS,
        OUTTYPE,
        PCHSCSCD,
        PK_CALBODY,
        PK_CKJLCID,
        PK_CORP,
        PK_DEPTDOC3,
        PK_INVBASDOC,
        PK_INVMANDOC,
        PK_PRODUCE,
        PK_PSNDOC3,
        PK_PSNDOC4,
        PK_RKJLCID,
        PK_SEALUSER,
        PK_STORDOC,
        PREVAHEAD,
        PRICEMETHOD,
        PRIMARYFLAG,
        PRIMNESSNUM,
        PRODUCEMETHOD,
        RATIONWTNUM,
        REALUSABLEAMOUNT,
        ROADTYPE,
        ROUNDINGNUM,
        SAFETYSTOCKNUM,
        SCHEATTR,
        SCPL,
        SCSCDDMS,
        SCXYBZSFZK,
        SEALDATE,
        SEALFLAG,
        SFBJ,
        SFCBDX,
        SFFZFW,
        SFPCHS,
        SFSCX,
        SFZB,
        SFZZCP,
        STOCKBYCHECK,
        STOCKLOWERDAYS,
        STOCKUPPERDAYS,
        SUMAHEAD,
        SUPPLYTYPE,
        TS,
        USABLEAMOUNT,
        USABLEAMOUNTBYFREE,
        VIRTUALFLAG,
        WASTERRATE,
        WGGDSCZKXS,
        WGHXCL,
        YBGYS,
        ZBCZJYXM,
        ZBXS,
        ZDHD,
        ZGYS
    )
VALUES
    (
        'A',
        'C',
        'C',
        'C',
        'C',
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        'ZJ',
        NULL,
        0,
        NULL,
        'N',
        NULL,
        NULL,
        NULL,
        'N',
        NULL,
        'N',
        '2023-06-19 15:41:53',
        '0001K81000000000E2YQ',
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        NULL,
        NULL,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        'N',
        'N',
        'N',
        'N',
        'N',
        'Y',
        'N',
        NULL,
        'N',
        'Y',
        'N',
        'Y',
        'N',
        'Y',
        NULL,
        0,
        0,
        NULL,
        0,
        2,
        'MR',
        NULL,
        NULL,
        1,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        'OA',
        0,
        '1005K81000000000099E',
        NULL,
        '1005',
        NULL,
        '0001H9100000000FSPWT',
        '0001H9100000000FSPWY',
        '0001H9100000000FSPWZ',
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        3,
        'N',
        NULL,
        0,
        0.5,
        NULL,
        0,
        0.5,
        NULL,
        NULL,
        NULL,
        0,
        'N',
        NULL,
        'N',
        NULL,
        'N',
        'N',
        'Y',
        NULL,
        'N',
        'N',
        'N',
        NULL,
        NULL,
        NULL,
        '0',
        '2023-06-19 15:41:53',
        '1111111111111011',
        'NNN',
        'N',
        NULL,
        NULL,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL
    );
```

---



## 修改分配

!> 仅可修改`保质期`、`退货根据检验结果入库`、`是否免检`三个字段；

### 商品管理档案

?> 若修改`保质期`、`退货根据检验结果入库`字段，则更新管理档案表；`BD_INVMANDOC`

仅根据商品管理档案主键更新以下字段值：

| 字段名称                     | 字段列名           | 赋值方式 | 值                                                | 示例                 |
| :--------------------------- | :----------------- | :------: | :------------------------------------------------ | :------------------- |
| 销售退货是否根据检验结果入库 | ISINVRETINSTOBYCHK |   变量   | 根据**退货根据检验结果入库**字段值进行赋值，默认N | N                    |
| 修改人                       | MODIFIER           |   变量   | 当前操作人员对应NC员工ID                          | 0001K81000000000E2YQ |
| 修改时间                     | MODIFYTIME         |   变量   | 当前时间                                          | 2023-06-19 15:41:53  |
| 保质期                       | QUALITYDAYNUM      |   变量   | 取值为保质期值                                    | 2                    |
| 是否保质期管理               | QUALITYMANFLAG     |   变量   | 保质期单位为”**无保质期**“时为N，否则Y            | Y                    |
| 保质期单位                   | QUALITYPERIODUNIT  |   变量   | 根据选择的单位赋值，<br />0,年  1,月              | 0                    |
| 时间戳                       | TS                 |   变量   | 当前时间                                          | 2023-06-19 15:41:53  |

SQL处理

```sql
UPDATE
	BD_INVMANDOC
SET
	ISINVRETINSTOBYCHK = '$取”退货根据检验结果入库“的值$',
	QUALITYDAYNUM = '$取值为保质期值$',
	QUALITYMANFLAG = '$保质期单位为”**无保质期**“时为N，否则Y$',
	QUALITYPERIODUNIT = '$根据选择的单位赋值，0-年，1-月$',
	MODIFIER = '当前操作人员对应NC员工ID',
	MODIFYTIME = '$当前时间$',
	TS = '$当前时间$'
WHERE
	PK_INVMANDOC = '$该商品分配记录中，管理档案的ID$';
```

### 物料生产档案

?> 若修改`是否免检`字段，则更新物料生产档案表；`BD_PRODUCE`

仅根据物料生产档案主键更新以下字段值：

| 字段名称 | 字段列名    | 赋值方式 | 值                                    | 示例                 |
| :------- | :---------- | :------: | :------------------------------------ | :------------------- |
| 是否免检 | CHKFREEFLAG |   变量   | 取值为表单中的**是否免检**字段，默认N | N                    |
| 修改人   | MODIFIER    |   变量   | 当前操作人员对应NC员工ID              | 0001K81000000000E2YQ |
| 修改时间 | MODIFYTIME  |   变量   | 当前时间                              | 2023-06-19 15:42:13  |
| 时间戳   | TS          |   变量   | 当前时间                              | 2023-06-19 15:42:13  |

SQL处理

```sql
UPDATE
	BD_PRODUCE
SET
	CHKFREEFLAG = '$取值为表单中的**是否免检**字段$',
	MODIFIER = '当前操作人员对应NC员工ID',
	MODIFYTIME = '$当前时间$',
	TS = '$当前时间$'
WHERE
	PK_PRODUCE = '$该商品分配记录中，物料生产档案的ID$';
```



## 删除分配

!> 删除分配时，严格按照顺序更新上述两个表的DR字段

```sql
/*删除商品管理档案记录*/
UPDATE
	BD_INVMANDOC
SET
	DR = 1
WHERE
	PK_INVMANDOC = '$该商品分配记录中，管理档案的ID$';

/*删除物料生产档案记录*/
UPDATE
	BD_PRODUCE
SET
	DR = 1
WHERE
	PK_PRODUCE = '$该商品分配记录中，物料生产档案的ID$';
```











