本服务等级协议（Service Level Agreement，以下简称 “SLA”）规定了京东云向客户提供的数据库备份服务DBS的可用性等级指标及赔偿方案。特别提示您本服务等级协议仅适用于DBS收费任务，DBS收费任务包括全量数据备份、增量日志备份，不包括数据恢复任务。

 **1.** **定义**

**服务周期：** 一个服务周期为一个自然月，不满一个自然月则以当月该单个DBS备份计划累计使用时间做为一个服务周期。

如您购买3个月本服务，服务开通日为3月17日，到期日为6月16日，则包含4个服务周期。第1个服务周期是指3月17日到3月31日，第2个服务周期是指4月1日到4月30日，第3个服务周期是指5月1日到5月31日，第4个服务周期是指6月1日到6月16日。服务可用性按服务周期单独核算

**服务周期总分钟数：** 按照服务周期内的总天数 * 24（小时）* 60（分钟）计算 

**服务不可用：** 在客户定义的全量备份时间后24小时仍然无任何数据备份到目的端，则视为DBS服务不可用。本次服务不可用分钟数为 60*24。在一个服务周期内单个DBS备份计划不可用分钟数之和即服务不可用分钟数。

**服务不可用分钟数：** 一个服务周期内单个DBS备份计划不可用分钟数之和即服务不可用分钟数。

**月度服务费：** 您在一个服务周期中就单个DBS备份计划所支付的服务费用总额，不包含已经购买尚未消费的部分。如果您一次性支付了多个月份的服务费用，则将按照所购买的月数分摊计算月度服务费用。

**2.** **服务保证指标**

**2.1** **服务可用性**

服务可用性以单个DBS备份计划为维度，按照如下方式计算：

服务可用性 = (**1 -** **服务不可用分钟数** **/** **服务周期总分钟数**) * 100%

**2.2** **服务可用性承诺**

京东云提供的本服务可用性不低于99.9%，如未达到上述可用性标准（属于免责条款情形的除外），您可以根据本协议第3条约定获得赔偿。赔偿范围不包括以下原因所导致的服务不可用时间：

（1）由于源端数据库自身原因不可用导致DBS无法读取源端数据库数据或日志，包括不限于如下情况，源端数据库由于空间超限被锁定、源端数据库由于主机宕机不可用、源端数据库由于连接数消耗殆尽导致无法连接、源端数据库资源耗尽导致不可服务或者不可稳定的提供服务等；

（2）由于目的端存储库自身原因不可用导致DBS无法写入数据，包括但不限于空间超限被锁定、资源耗尽导致不可服务或者不可稳定的提供服务等；

（3）由于源端数据库用户名、密码被修改或者目的端存储Access Key被修改，导致DBS连接不可用；

（4）由于源端数据库或者目的端存储被删除，导致DBS任务不可用；

（5）针对备份代理，由于客户环境不稳定、操作不当引起的；

（6）客户的疏忽或由客户授权的操作所引起的；

（7）客户未遵循京东云产品使用文档或使用建议引起的；

（8）不可抗力引起的。

**2.3** **免责条款**

因京东云故障导致DBS备份计划无法正常使用，以及京东云故障引起的网站无法正常访问，京东云将对不可用时间进行赔偿，但不包括以下原因所导致的服务不可用时间：

（1）预先通知用户后进行系统维护所引起的，如割接、升级、模拟故障演练等计划内停机时间。

（2）任何京东云所属设备以外的网络、设备故障或配置调整引起的。

（3）京东云以外第三方引起的，例如遭受黑客攻击、或您第三方供应商疏忽导致的不可用等。

（4）您维护不当或保密不当致使数据、口令、密码等丢失或泄漏所引起的。

（5）您的疏忽导致的误操作或由您授权的操作所引起的。例如，用户主动重启、发起迁移等操作。

（6）您未遵循京东云产品使用文档或使用建议引起的。

（7）非京东云原因造成的服务不可用或服务不达标的情况。

（8）属于相关法律法规、相关协议、相关规则或京东云单独发布的相关规则、说明等中所述的京东云可以免责、免除赔偿责任等的情况。

（9）其他不可抗力引起的。

**3.** **赔偿方案**

对于本服务，如服务可用性低于标准，您有权按照如下条款约定获得赔偿：

**3.1** **赔偿标准**

（1）赔偿以京东云发放代金券的形式实现，您应当遵守代金券的使用规则（包括使用期限等，具体以京东云官网发布的代金券相关规则为准）。发放的代金券不能折现、不开具发票，仅限您通过您的京东云账户购买本服务，不能购买其他的京东云服务，您也不可以将代金券进行转让、赠予等。

（2）如果某服务周期没有达到服务可用性标准，赔偿额按照相应未达标服务周期单独计算，赔偿总额不超过相应未达标服务周期内您就本服务支付的相应月度服务费（此处的月度服务费不含用代金券、优惠券、服务费减免等抵扣的费用）。

DBS赔偿标准：

| **服务周期的服务可用性**     | **赔偿**           |
| ---------------------------- | ------------------ |
| 低于99.95%但等于或高于99.00% | 月度服务费用的15%  |
| 低于99.00%但等于或高于95.00% | 月度服务费用的30%  |
| 低于95%                      | 月度服务费用的100% |

**3.2** **赔偿申请时限**

（1）您可以在没有达标的相应服务周期结束后的次月的第五（5）个工作日后，仅通过您相应账户的工单系统提出赔偿申请。您提出赔偿申请后京东云会进行相应核实，对于服务周期的服务可用性的计算，若双方出现争议的，双方均同意最终以京东云的后台记录为准。

（2）赔偿申请必须限于在DBS备份计划没有达到可用性的相关月份结束后六十（60）日内提出。超出申请时限的赔偿申请将不被受理。

**3.3** **赔偿申请材料**

如果您认为本服务未达到服务可用性标准的，您可以按照本服务等级协议中规定的时限发起赔偿申请。您的赔偿申请需至少与下列信息一同提供：

（1）服务不可用的DBS数据库备份计划 ID。

（2）服务不可用时长及其他相关证明。

**4** **其他**

4.1 双方确认并在此认可：在任何情况下，若您在使用本服务过程中因京东云违约原因造成您损失的，京东云的违约赔偿总额不超过您已经支付的相应违约服务对应的服务费总额。

4.2 京东云有权根据变化适时或必要时对本SLA条款作出修改。如本SLA条款有任何修改，您可以在京东云官网的最新版本中查阅相关协议条款。如您不同意京东云对协议所做的修改，您有权停止使用本服务，如您继续使用本服务，则视为您接受修改后的SLA。

4.3 本协议作为《京东云服务协议》的附属协议，具有与《京东云服务协议》同等效力，本协议未约定事项，您需遵守《京东云服务协议》的相关约定。若本协议与《京东云服务协议》中的条款相冲突或不一致，则以本协议为准，但仅在该冲突或不一致范围内适用。

