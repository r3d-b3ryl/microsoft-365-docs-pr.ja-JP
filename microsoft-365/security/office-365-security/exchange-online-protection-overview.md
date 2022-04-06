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
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Exchange Online Protection (EOP) が、スタンドアロンおよびハイブリッド環境でオンプレミスのメール組織を保護するのにどのように役立つかを説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3fb49a24ae378be990efd727450a06889cc50679
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473367"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) は、スパム、マルウェア、その他のメールの脅威から組織を保護するクラウドベースのフィルタリング サービスです。 EOP は、Exchange Online メールボックスを持つすべての Microsoft 365 組織に含まれています。

> [!NOTE]
> EOP は、オンプレミスのメールボックスを保護するために単独で、またはハイブリッド環境でオンプレミスの Exchange メールボックスを保護するために使用することもできます。 詳細については、「[スタンドアロン Exchange Online Protection](/exchange/standalone-eop/standalone-eop)」を参照してください。

EOP セキュリティ機能を設定する手順と、Microsoft Defender for Office 365 で取得できる追加のセキュリティとの比較については、「[脅威から保護する](protect-against-threats.md)」を参照してください。 EOP 機能の推奨設定は、「[EOP および Microsoft Defender for Office 365 セキュリティの推奨設定](recommended-settings-for-eop-and-office365.md)」にあります。

この記事の残りの部分では、EOP の仕組みと EOP で使用できる機能について説明します。

## <a name="how-eop-works"></a>EOP の仕組み

EOP の仕組みを理解すると、受信メールの処理方法がわかりやすくなります。

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="迷惑メールまたは検疫、またはエンド ユーザーのメール配信のいずれかの判定の前に、接続、マルウェア対策、メールフロー ルール スラッシュ ポリシー フィルター、およびコンテンツ フィルターを介して EOP に渡される、インターネットまたは顧客のフィードバックのいずれかからのメールの図" lightbox="../../media/tp_emailprocessingineopt3.png":::

1. 受信メッセージが EOP に入ると、最初に接続フィルターに渡され、送信者の評判が確認されます。 スパムの大半はこの時点で停止され、EOP によって拒否されます。 詳細については、「[接続フィルターを構成する](configure-the-connection-filter-policy.md)」を参照してください。

2. 次に、メッセージのマルウェア検査が行われます。 メッセージまたは添付ファイルにマルウェアが見つかった場合、メッセージは検疫に配信されます。 既定では、管理者のみがマルウェア検疫済みメッセージを表示および操作できます。 ただし、管理者は[検疫ポリシー](quarantine-policies.md)を作成し、使用して、検疫済みメッセージに対してユーザーが実行できる操作を指定できます。 マルウェア対策保護の詳細については、「[EOP のマルウェア対策保護](anti-malware-protection.md)」を参照してください。

3. メッセージはポリシー フィルターを通じて続行され、作成したメール フロー ルール (トランスポート ルールとも呼ばれます) に対して評価されます。 たとえば、ルールは、特定の送信者からメッセージが到着したときにマネージャーに通知を送信できます。

   Exchange Enterprise CAL with Services ライセンスを持つオンプレミスの組織では、EOP の [データ損失防止 (DLP)](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) チェックもこの時点で行われます。

4. メッセージは、有害なメッセージがスパム、高確度スパム、フィッシング、高確度フィッシング、またはバルク (スパム対策ポリシー) またはスプーフィング (フィッシング対策ポリシーのスプーフィング設定) として識別されるコンテンツ フィルター (スパム対策とスプーフィング対策) を通過します。 フィルターの判定 (検疫、迷惑メール フォルダーへの移動など) に基づいてメッセージに対して実行するアクションを構成できます。また、[検疫ポリシー](quarantine-policies.md)を使用して、検疫済みメッセージに対してユーザーが実行できる操作構成できます。 詳細については、「[EOP のスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」および「[EOP のフィッシング対策ポリシーの構成](configure-anti-phishing-policies-eop.md)」を参照してください。

メッセージが、これらの保護層すべてを問題なくパスすると、受信者に配信されます。

詳細については、「[メール保護の順序と優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

### <a name="eop-datacenters"></a>EOP データセンター

EOP は、最良の可用性を提供するために設計された複数のデータセンターから成る世界規模のネットワーク上で稼働します。たとえば、あるデータセンターが使用できなくなった場合、メール メッセージはサービスを中断することなく、自動的に別のデータセンターにルーティングされます。各データセンターのサーバーがユーザーの代わりにメッセージを受け付け、組織とインターネットの間を分離するレイヤーが提供されるため、組織のサーバーの負荷が軽減されます。この高可用性のネットワークによって、Microsoft は適切なタイミングで組織にメールが配信されることを保証できます。

EOP はデータセンター間の負荷分散を実行しますが、1 つの地域内でのみ行います。 1 つの地域でサービスが提供されている場合は、すべてのメッセージがその地域のメール ルーティングを使用して処理されます。

### <a name="eop-features"></a>EOP の機能

このセクションでは、EOP で使用できる主な機能の概要について説明します。

すべての EOP サブスクリプション プランの要件、重要な制限、および機能の利用可能性の詳細については、「[Exchange Online Protection サービスの説明](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)」を参照してください。

**注**:

- EOP では、メッセージ内の既知の悪意のあるリンクを検出するため、いくつかの URL 禁止リストを使用しています。
- EOP では、スパムを送信することが知られているドメインの膨大なリストを使用します。
- EOP では、複数のマルウェア対策エンジンを使用して、お客様を常に自動的に保護します。
- EOP は、メッセージ本文とすべての添付ファイルのアクティブなペイロードにマルウェアがないか検査します。
- 保護ポリシーの推奨される値については、「[EOP および Microsoft Defender for Office 365 セキュリティの推奨設定](recommended-settings-for-eop-and-office365.md)」を参照してください。
- 保護ポリシーを構成する簡単な手順については、「[脅威から保護する](protect-against-threats.md)」を参照してください。

|機能|コメント|
|---|---|
|**Protection**||
|マルウェア対策|[EOP のマルウェア対策保護](anti-malware-protection.md) <p> [マルウェア対策保護のよく寄せられる質問](anti-malware-protection-faq-eop.yml) <p> [EOP のマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)|
|受信スパム対策|[EOP のスパム対策保護](anti-spam-protection.md) <p> [スパム対策保護に関してよく寄せられる質問](anti-spam-protection-faq.yml) <p> [EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
|送信スパム対策|[EOP の送信スパム保護](outbound-spam-controls.md) <p> [EOP の送信スパム フィルターを構成する](configure-the-outbound-spam-policy.md) <p> [Microsoft 365 で外部メールの自動転送を制御する](external-email-forwarding.md)|
|接続フィルター|[接続フィルターの構成](configure-the-connection-filter-policy.md)|
|フィッシング詐欺対策|[Microsoft 365 のフィッシング詐欺対策ポリシー](set-up-anti-phishing-policies.md) <p> [EOP でのスパム対策ポリシーの構成](configure-anti-phishing-policies-eop.md)|
|スプーフィング対策保護|詳細については、「[EOP のスプーフィング インテリジェンス分析](learn-about-spoof-intelligence.md)」を参照してください。 <p> [テナントの許可/禁止リストを管理する](tenant-allow-block-list.md)|
|配信されたスパム、マルウェア、フィッシング メッセージのゼロアワー自動消去 (ZAP)|[Exchange Online のゼロアワー自動消去](zero-hour-auto-purge.md)|
|事前設定されたセキュリティ ポリシー|[EOP と Microsoft Defender for Office 365 の事前設定されたセキュリティ ポリシー](preset-security-policies.md) <p> [EOP および Defender for Office 365 の構成アナライザー](configuration-analyzer-for-security-policies.md)|
|テナントの許可/禁止リスト|[テナントの許可/禁止リストを管理する](tenant-allow-block-list.md)|
|メッセージ送信者の受信拒否一覧|[EOP で受信拒否送信者の一覧を作成する](create-block-sender-lists-in-office-365.md)|
|メッセージ送信者の受信許可一覧|[EOP で安全な差出人のリストを作成する](create-safe-sender-lists-in-office-365.md)|
|Directory Based Edge Blocking (DBEB)|[ディレクトリ ベースのエッジ ブロックを使用して無効な受信者に送信されたメッセージを拒否する](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|
|**検疫と報告**||
|管理者による報告|[管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する](admin-submission.md)|
|ユーザーからの報告 (カスタム メールボックス)|[ユーザーからの報告ポリシー](user-submission.md)|
|検疫 - 管理者|[EOP の管理者として検疫済みメッセージとファイルを管理する](manage-quarantined-messages-and-files.md) <p> [検疫済みメッセージに関する FAQ](quarantine-faq.yml) <p> [メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md) <p> [Microsoft 365 のスパム対策メッセージ ヘッダー](anti-spam-message-headers.md) <p> 検疫済みメッセージのメッセージ ヘッダーは、[メッセージ ヘッダー アナライザー](https://mha.azurewebsites.net/)を使用して分析できます。|
|検疫 - エンドユーザー|[EOP のユーザーとして検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md) <p> [検疫通知を使用して検疫済みメッセージを解放および報告する](use-spam-notifications-to-release-and-report-quarantined-messages.md) <p> [検疫ポリシー](quarantine-policies.md)|
|**メール フロー**||
|メール フロー ルール|[Exchange Online のメール フロー ルール (トランスポート ルール)](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) <p> [Exchange Online のメール フロー ルールでの条件と例外 (述語)](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions) <p> [Exchange Online でのメール フロー ルールの処理](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions) <p> [Exchange Online のメール フロー ルールを管理する](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) <p> [Exchange Online のメール フロー ルールの手順](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-procedures)|
|承認済みドメイン|[Exchange Online で承認済みドメインを管理する](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)|
|コネクタ|[Exchange Online でコネクタを使用してメール フローを構成する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)|
|コネクタのフィルター処理の強化|[Exchange Online のコネクタのフィルター処理の強化](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)|
|**監視**||
|メッセージの追跡|[メッセージの追跡](message-trace-scc.md) <p> [Exchange 管理センターでのメッセージ追跡](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)|
|メールと共同作業に関するレポート|[メール セキュリティ レポートを表示する](view-email-security-reports.md)|
|メール フロー レポート|[メール フロー レポートを表示する](view-mail-flow-reports.md) <p> [Exchange 管理センターのメール フロー レポート](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|メール フローの分析情報|[メール フローの分析情報](mail-flow-insights-v2.md) <p> [Exchange 管理センターのメール フローの分析情報](/exchange/monitoring/mail-flow-insights/mail-flow-insights)|
|監査レポート|[Exchange 管理センターの監査レポート](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)|
|ポリシーを通知する|[通知ポリシー](../../compliance/alert-policies.md)|
|**サービス レベル アグリーメント (SLA) とサポート**||
|スパム有効性 SLA|\> 99%|
|偽陽性率 SLA|\< 1:250,000|
|ウイルス検出とブロックする SLA|既知のウイルスの 100%|
|月間稼働時間 SLA|99.999%|
|1 日 24 時間、週 7 日の電話および Web テクニカル サポート|[EOP のヘルプとサポート](help-and-support-for-eop.md)。|
|**その他の機能**||
|サーバーの地域冗長グローバル ネットワーク|EOP は、最適な可用性を提供するよう設計された、複数のデータ センターから成る世界規模のネットワーク上で稼働します。 詳細については、この記事の前半の「[EOP データセンター](#eop-datacenters)」セクションを参照してください。|
|社内サーバーでメールが受信できない場合のメッセージ キュー|保留にされたメッセージはキュー内で 1 日間保持されます。 メッセージの再試行は、受信者のメールシステムから返されたエラーに基づいて行われます。 平均では、5 分ごとにメッセージの送信が再試行されます。 詳細については、「[EOP のキューイング、保留、返送されるメッセージに関する FAQ](eop-queued-deferred-and-bounced-messages-faq.yml)」を参照してください。|
|アドオンとして利用可能な Office 365 Message Encryption|詳細については、「[Office 365 での暗号化](../../compliance/encryption.md)」をご覧ください。|
|||
