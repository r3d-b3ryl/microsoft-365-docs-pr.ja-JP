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
ms.openlocfilehash: ce90f1429e2c54f413ae54172a6d2f663ef6a358
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624732"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) は、スパム、マルウェア、その他の電子メールの脅威から組織を保護するのに役立つクラウドベースのフィルター サービスです。 EOP は、すべての組織Microsoft 365メールボックスExchange Onlineされます。

この記事の残りの部分では、EOP のしくみについて説明します。

> [!NOTE]
> EOP は、オンプレミスのメールボックスを保護するために、およびハイブリッド環境でオンプレミスのメールボックスを保護するためにExchangeもあります。 詳細については、「スタンドアロン サーバー」[を参照Exchange Online Protection。](/exchange/standalone-eop/standaonline-eop)

## <a name="how-eop-works"></a>EOP の仕組み

EOP の仕組みを理解すると、受信メールの処理方法がわかりやすくなります。

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="迷惑メールまたは検疫、またはエンド ユーザーのメール配信の判断前に、インターネットからの電子メールまたは顧客からのフィードバックが EOP に渡され、接続、マルウェア対策、Mailflow Rules-slash-Policy Filtering、およびコンテンツ フィルター処理を通じて送信されたメールのグラフィック。":::

- 受信メッセージが EOP に入った場合、最初は接続フィルターを通過し、送信者の評判をチェックします。 スパムの大部分はこの時点で停止され、EOP によって拒否されます。 詳細については、「[接続フィルターを構成する](configure-the-connection-filter-policy.md)」を参照してください。

- 次に、メッセージがマルウェアの検査を受け取ります。 メッセージまたは添付ファイルにマルウェアが見つかった場合、メッセージは管理者専用の検疫ストアにルーティングされます。 マルウェア保護の詳細については [、「EOP のマルウェア対策保護」を参照してください](anti-malware-protection.md)。

- メッセージはポリシー フィルター処理を続け、テンプレートから作成または適用するカスタム メール フロー ルール (トランスポート ルールとも呼ばれる) に対して評価されます。 たとえば、特定の送信者からメールが届いたときにマネージャーに通知を送信するルールを設定できます。 データ損失防止 (DLP) チェックは、この時点でも発生します (Exchange Enterprise CAL with Services)。

- 次に、メッセージがスパム、フィッシング、またはバルク メールのチェックを行うスパム対策フィルターを通過します。 検出されたメッセージは、検疫、またはユーザーの迷惑メール フォルダーなど、他のオプションに送信できます。 詳細については、「 [スパム対策ポリシーを構成する](configure-your-spam-filter-policies.md) 」および「フィッシング対策ポリシーを構成 [する」を参照してください](configure-anti-phishing-policies-eop.md)。

これらすべての保護層を正常に通過するメッセージは、受信者に配信されます。

詳細については、「メール保護の [順序と優先順位」を参照してください](how-policies-and-protections-are-combined.md)。

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>オンプレミスの電子メール組織の EOP プランと機能

利用可能な EOP サブスクリプション プランは次のとおりです。

- **EOP スタンドアロン**: オンプレミスの電子メール組織を保護するために EOP に登録します。

- **Exchange Online の EOP** 機能: Exchange Online (スタンドアロンまたは Microsoft 365 の一部として) を含むサブスクリプションでは、EOP を使用して、Exchange Online メールボックスを保護します。

- **Exchange Enterprise CAL with Services**: 追加の Exchange Enterprise CAL with Services ライセンスを購入したオンプレミスの Exchange 組織がある場合、EOP は付属のサービスの一部です。

すべての EOP サブスクリプション プランの要件、重要な制限、および機能の可用性については[、「Exchange Online Protection」を参照してください](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

> [!NOTE]
> メールボックスを含むMicrosoft 365またはOffice 365サブスクリプションがあるExchange Online EOP があります。 サブスクリプションで EOP セキュリティ機能をセットアップする手順と、microsoft Defender for Office 365 サブスクリプションが提供できる追加のセキュリティに関する情報については、「脅威から保護する」を[参照してください](protect-against-threats.md)。 セットアップ用の EOP 機能の推奨設定については、「EOP および Microsoft Defender のセキュリティに関する推奨設定」[をOffice 365してください](recommended-settings-for-eop-and-office365.md)。

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>オンプレミスの電子メール組織の EOP のセットアップ

EOP のセットアップは、特にコンプライアンス ルールが少ない小規模な組織の場合に、シンプルにすることができます。ただし、複数ドメイン、カスタム コンプライアンス ルール、またはハイブリッド メール フローが存在する大規模な組織の場合は、セットアップにより多くの計画や時間が必要となることがあります。

すでに EOP を購入している場合は、「[EOP サービスを設定する](/exchange/standalone-eop/set-up-your-eop-service)」を参照して、メッセージング環境を保護するように EOP を構成するために必要なすべての手順が完了していることを確認してください。

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

## <a name="eop-help-for-admins"></a>管理者向け EOP ヘルプ

EOP 管理者向けのヘルプ コンテンツは、次の最上位カテゴリで構成されます。

- Microsoft Defender for Office 365 管理者向け[EOP、Day 1](protect-against-threats.md)を構成する : Microsoft Defender for Office 365 の中核となる EOP 保護と検出ツールの構成。

- [EOP 機能: EOP](eop-features.md)で使用できる機能の一覧を提供します。

- [EOP サービスのセットアップ](/exchange/standalone-eop/set-up-your-eop-service): EOP サービスをセットアップするための手順と、追加情報へのリンクを提供します。

- [Google Postini、Barracuda Spam and Virus Firewall、または Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)から EOP に切り替える : 別の電子メール保護製品から EOP に切り替えるプロセスについて説明します。

- [スタンドアロン EOP で受信者を管理](/exchange/standalone-eop/manage-recipients-in-eop)する : スタンドアロン EOP でメール ユーザーとグループを管理する方法について説明します。

- [EOP](mail-flow-in-eop.md)のメール フロー: コネクタを使用してカスタム メール フロー シナリオを構成する方法、サービスに関連付けられているドメインを管理する方法、およびディレクトリ ベースのエッジ ブロック (DBEB) 機能を有効にする方法について説明します。

- [EOP と Microsoft Defender](recommended-settings-for-eop-and-office365.md)のセキュリティに関する推奨設定Office 365: サービスをセットアップおよびプロビジョニングした後の推奨される構成設定と考慮事項について説明します。

- [[監査レポート] Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports): 監査レポートを使用してサービスの構成変更を追跡する方法について説明します。

- [EOP でのスパム](anti-spam-and-anti-malware-protection.md)対策とマルウェア対策の保護: スパム フィルターとマルウェア フィルターについて説明し、組織のニーズに最も合わせてカスタマイズする方法を示します。 また、管理者とエンド ユーザーが検疫済みメッセージに対して実行可能なタスクについても説明しています。

- [[レポートとメッセージの追跡](reporting-and-message-trace-in-exchange-online-protection.md)Exchange Online Protection: 使用可能なレポートとトラブルシューティング ツールについて説明します。

- [Exchange EOP](/exchange/exchange-admin-center)の Exchange Online または Exchange 管理センターの管理センター : 関連する[EOP](/exchange/standalone-eop/exchange-admin-center-eop)機能を管理するために、Exchange 管理センター (EAC) 管理インターフェイスにアクセスして移動する方法について説明します。

- [Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell): リモート PowerShell に関する情報を提供します。これにより、コマンド ラインから EOP サービスを管理できます。

- 「[EOP のヘルプとサポート](help-and-support-for-eop.md)」 ヘルプおよびテクニカル サポートの入手方法について説明しています。