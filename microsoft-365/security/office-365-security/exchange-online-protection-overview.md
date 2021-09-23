---
title: Exchange Online Protection (EOP) の概要
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: スタンドアロン環境Exchange Online Protectionハイブリッド環境で、EOP (EOP) がオンプレミスの電子メール組織を保護する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 006be2cf23735f6ec44c749de869e87d55be2123
ms.sourcegitcommit: 0ed93816e2c1e6620e68bd1c0f00390062911606
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2021
ms.locfileid: "59483101"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) は、スパム、マルウェア、その他の電子メールの脅威から組織を保護するクラウドベースのフィルター サービスです。 EOP は、すべての組織Microsoft 365メールボックスExchange Onlineされます。

> [!NOTE]
> EOP は、オンプレミスのメールボックスを保護するために、およびハイブリッド環境でオンプレミスのメールボックスを保護するためにExchangeもあります。 詳細については、「スタンドアロン サーバー」[を参照Exchange Online Protection。](/exchange/standalone-eop/standalone-eop)

EOP セキュリティ機能をセットアップする手順と、Microsoft Defender で使用するセキュリティと比較する手順については、「Office 365の保護」を[参照してください](protect-against-threats.md)。 EOP 機能の推奨設定は、「EOP および Microsoft Defender のセキュリティに関する推奨設定[」でOffice 365使用できます](recommended-settings-for-eop-and-office365.md)。

この記事の残りの部分では、EOP のしくみと EOP で使用できる機能について説明します。

## <a name="how-eop-works"></a>EOP の仕組み

EOP の仕組みを理解すると、受信メールの処理方法がわかりやすくなります。

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="迷惑メールまたは検疫、またはエンド ユーザーのメール配信の判断前に、インターネットからの電子メールまたは顧客からのフィードバックが EOP に渡され、接続、マルウェア対策、Mailflow Rules-slash-Policy Filtering、およびコンテンツ フィルター処理を通じて送信されたメールのグラフィック。":::

1. 受信メッセージが EOP に入った場合、最初は接続フィルターを通過し、送信者の評判をチェックします。 スパムの大部分はこの時点で停止され、EOP によって拒否されます。 詳細については、「[接続フィルターを構成する](configure-the-connection-filter-policy.md)」を参照してください。

2. 次に、メッセージがマルウェアの検査を受け取ります。 メッセージまたは添付ファイルにマルウェアが見つかった場合、メッセージは検疫に配信されます。 既定では、マルウェア検疫済みメッセージを表示および操作できるのは管理者のみです。 ただし、管理者は検疫ポリシーを作成[](quarantine-policies.md)して使用して、検疫されたメッセージに対してユーザーが実行できる操作を指定できます。 マルウェア保護の詳細については [、「EOP のマルウェア対策保護」を参照してください](anti-malware-protection.md)。

3. メッセージはポリシー フィルター処理を通じて続行され、作成したメール フロー ルール (トランスポート ルールとも呼ばれる) に対して評価されます。 たとえば、ルールは、特定の送信者からメッセージが届いたときに、マネージャーに通知を送信できます。

   サービス ライセンスを持つ CAL Exchange Enterpriseオンプレミス組織では、EOP でのデータ損失防止[(DLP)](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)チェックもこの時点で行います。

4. メッセージは、有害なメッセージがスパム、高信頼スパム、フィッシング、高信頼フィッシング、またはバルク (スパム対策ポリシー) またはスプーフィング (フィッシング対策ポリシーのスプーフィング設定) として識別されるコンテンツ フィルター (スパム対策とスプーフィング対策) を通過します。 フィルター処理の評決 (検疫、迷惑メール フォルダーへの移動など)、および検疫ポリシーを使用して検疫されたメッセージに対してユーザーが実行できる操作に基づいて、メッセージに対して実行するアクションを [構成](quarantine-policies.md)できます。 詳細については、「スパム対策ポリシーを [構成する](configure-your-spam-filter-policies.md) 」および「EOP でフィッシング対策ポリシーを構成する」 [を参照してください](configure-anti-phishing-policies-eop.md)。

これらすべての保護層を正常に通過するメッセージが受信者に配信されます。

詳細については、「メール保護の [順序と優先順位」を参照してください](how-policies-and-protections-are-combined.md)。

### <a name="eop-datacenters"></a>EOP データセンター

EOP は、最良の可用性を提供するために設計された複数のデータセンターから成る世界規模のネットワーク上で稼働します。 たとえば、あるデータセンターが使用できなくなった場合、電子メール メッセージはサービスの中断なく、自動的に別のデータセンターにルーティングされます。 各データセンター内のサーバーは、ユーザーに代わってメッセージを受け入れ、組織とインターネットの間で一層の分離を提供し、サーバーの負荷を軽減します。 この高可用性のネットワークによって、Microsoft は適切なタイミングで組織に電子メールが配信されることを保証できます。

EOP はデータセンター間の負荷分散を実行しますが、1 つの地域内でのみ行います。1 つの地域でサービスが提供されている場合は、すべてのメッセージがその地域のメール ルーティングを使用して処理されます。EOP データセンターの地域メール ルーティングの動作を以下に示します。

- ヨーロッパ、中東、およびアフリカ (EMEA) では、すべての Exchange Online メールボックスが EMEA データセンターに配置され、すべてのメッセージが EOP フィルター処理のために EMEA データセンター経由でルーティングされます。
- APAC Asia-Pacificでは、すべての Exchange Online メールボックスは APAC データセンターにあり、メッセージは現在、EOP フィルター処理のために APAC データセンターを介してルーティングされます。
- 南北アメリカでは、サービスは次の場所に配布されます。
  - 南アメリカ: Exchange Onlineは、ブラジルとチリのデータセンターに配置されます。 すべてのメッセージは、EOP フィルター処理のためにローカル データセンター経由でルーティングされます。 検疫されたメッセージは、テナントが配置されているデータセンターに格納されます。
  - カナダ: Exchange Onlineメールボックスはカナダのデータセンターに配置されます。 すべてのメッセージは、EOP フィルター処理のためにローカル データセンター経由でルーティングされます。 検疫されたメッセージは、テナントが配置されているデータセンターに格納されます。
  - 米国: Exchange Onlineメールボックスは米国のデータセンターに配置されます。 すべてのメッセージは、EOP フィルター処理のためにローカル データセンター経由でルーティングされます。 検疫されたメッセージは、テナントが配置されているデータセンターに格納されます。
- Government Community Cloud (GCC) では、すべての Exchange Online メールボックスが米国データセンターに配置され、すべてのメッセージが EOP フィルター処理のために米国データセンター経由でルーティングされます。

### <a name="eop-features"></a>EOP の機能

このセクションでは、EOP で使用できる主な機能の概要について説明します。

すべての EOP サブスクリプション プランの要件、重要な制限、および機能の可用性については[、「Exchange Online Protection」を参照してください](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

**注**:

- EOP では、メッセージ内の既知の悪意のあるリンクを検出するため、いくつかの URL 禁止リストを使用しています。
- EOP は、スパムを送信することが知られているドメインの膨大なリストを使用します。
- EOP は、複数のマルウェア対策エンジンを使用して、お客様を自動的に保護します。
- EOP は、メッセージ本文のアクティブなペイロードと、すべてのメッセージ添付ファイルでマルウェアを検査します。
- 保護ポリシーの推奨値については、「EOP と Microsoft Defender のセキュリティに関する推奨設定[」をOffice 365してください](recommended-settings-for-eop-and-office365.md)。
- 保護ポリシーを構成する簡単な手順については、「脅威から保護 [する」を参照してください](protect-against-threats.md)。

<br>

****
|機能|コメント|
|---|---|
|**Protection**||
|マルウェア対策|[EOP のマルウェア対策保護](anti-malware-protection.md) <p> [マルウェア対策保護のよく寄せられる質問](anti-malware-protection-faq-eop.yml) <p> [EOP でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)|
|受信スパム対策|[EOP でのスパム対策保護](anti-spam-protection.md) <p> [スパム対策保護に関してよく寄せられる質問](anti-spam-protection-faq.yml) <p> [EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
|送信スパム対策|[EOP の送信スパム保護](outbound-spam-controls.md) <p> [EOP で送信スパム フィルターを構成する](configure-the-outbound-spam-policy.md) <p> [外部メールの自動転送を制御Microsoft 365](external-email-forwarding.md)|
|接続フィルター|[接続フィルターの構成](configure-the-connection-filter-policy.md)|
|フィッシング詐欺対策|[アプリ内のフィッシング対策Microsoft 365](set-up-anti-phishing-policies.md) <p> [EOP でのスパム対策ポリシーの構成](configure-anti-phishing-policies-eop.md)|
|スプーフィング対策保護|[EOP でのスプーフィング インテリジェンスの分析情報](learn-about-spoof-intelligence.md) <p> [テナントの許可/禁止リストを管理する](tenant-allow-block-list.md)|
|配信されたマルウェア、スパム、フィッシング メッセージのゼロ時間自動削除 (ZAP)|[ZAP in Exchange Online](zero-hour-auto-purge.md)|
|事前設定されたセキュリティ ポリシー|[EOP と Microsoft Defender でセキュリティ ポリシーを事前に設定Office 365](preset-security-policies.md) <p> [EOP および Microsoft Defender の保護ポリシー用の構成Office 365](configuration-analyzer-for-security-policies.md)|
|テナントの許可/禁止リスト|[テナントの許可/禁止リストを管理する](tenant-allow-block-list.md)|
|メッセージ送信者のリストをブロックする|[EOP で受信拒否リストを作成する](create-block-sender-lists-in-office-365.md)|
|メッセージ送信者のリストを許可する|[EOP で差出人セーフ リストを作成する](create-safe-sender-lists-in-office-365.md)|
|Directory Based Edge Blocking (DBEB)|[ディレクトリ ベースのエッジ ブロックを使用して無効な受信者に送信されたメッセージを拒否する](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|
|**検疫と申請**||
|管理者の申請|[管理者申請を使用して、疑わしいスパム、フィッシング、URL、ファイルを Microsoft に提出する](admin-submission.md)|
|ユーザー申請 (カスタム メールボックス)|[ユーザー申請ポリシー](user-submission.md)|
|検疫 - 管理者|[EOP の管理者として検疫済みメッセージとファイルを管理する](manage-quarantined-messages-and-files.md) <p> [検疫済みメッセージに関するよく寄せられる質問](quarantine-faq.yml) <p> [メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md) <p> [Microsoft 365 のスパム対策メッセージ ヘッダー](anti-spam-message-headers.md) <p> 検疫済みメッセージのメッセージ ヘッダーは、次のメッセージ ヘッダー アナライザー [を使用して分析できます](https://mha.azurewebsites.net/)。|
|検疫 - エンド ユーザー|[EOP のユーザーとして検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md) <p> [検疫通知を使用して検疫済みメッセージを解放および報告する](use-spam-notifications-to-release-and-report-quarantined-messages.md) <p> [検疫ポリシー](quarantine-policies.md)|
|**メール フロー**||
|メール フロー ルール|[Exchange Online のメール フロー ルール (トランスポート ルール)](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) <p> [Exchange Online のメール フロー ルールでの条件と例外 (述語)](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions) <p> [Exchange Online でのメール フロー ルールの処理](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions) <p> [Exchange Online のメール フロー ルールを管理する](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) <p> [メール フロー ルールの手順 (Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-procedures)|
|承認済みドメイン|[Exchange Online で承認済みドメインを管理する](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)|
|コネクタ|[コネクタを使用してメール フローを構成Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)|
|コネクタのフィルター処理の強化|[コネクタの拡張フィルター Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)|
|**監視**||
|メッセージの追跡|[メッセージの追跡](message-trace-scc.md) <p> [管理センターのExchangeトレース](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)|
|メール&コラボレーション レポート|[メール セキュリティ レポートを表示する](view-email-security-reports.md)|
|メール フロー レポート|[メール フロー レポートを表示する](view-mail-flow-reports.md) <p> [管理センターのメール フロー Exchangeレポート](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|メール フローの分析情報|[メール フローの分析情報](mail-flow-insights-v2.md) <p> [管理センターでのメール フロー Exchange分析情報](/exchange/monitoring/mail-flow-insights/mail-flow-insights)|
|監査レポート|[管理センターでのExchange監査](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)|
|ポリシーを通知する|[通知ポリシー](../../compliance/alert-policies.md)|
|**サービス レベル アグリーメント (SLA) とサポート**||
|スパム有効性 SLA|\> 99%|
|偽陽性率 SLA|\< 1:250,000|
|ウイルス検出とブロックする SLA|既知のウイルスの 100%|
|月間稼働時間 SLA|99.999%|
|1 日 24 時間、週 7 日の電話および Web テクニカル サポート|[EOP のヘルプとサポート](help-and-support-for-eop.md)。|
|**その他の機能**||
|サーバーの地域冗長グローバル ネットワーク|EOP は、最適な可用性を提供するよう設計された、複数のデータ センターから成る世界規模のネットワーク上で稼働します。 詳細については、この記事の [「EOP データセンター」](#eop-datacenters) セクションを参照してください。|
|社内サーバーでメールが受信できない場合のメッセージ キュー|遅延中のメッセージは、キューに 1 日残ります。 メッセージの再試行は、受信者のメールシステムから返されたエラーに基づいて行われます。 平均では、5 分ごとにメッセージの送信が再試行されます。 詳細については、「[EOP のキューイング、保留、返送されるメッセージに関する FAQ](eop-queued-deferred-and-bounced-messages-faq.yml)」を参照してください。|
|Office 365 Message Encryptionとして利用できる場合|詳細については、「[Office 365 での暗号化](../../compliance/encryption.md)」をご覧ください。|
|||
