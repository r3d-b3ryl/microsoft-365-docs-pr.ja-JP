---
title: Microsoft Defender for Office 365 を評価する
description: 評価モードOffice 365 Defender は、マルウェアなどのOffice 365をログに記録するが、メッセージに対して動作しない電子メール ポリシー用の Defender を作成します。
keywords: 評価Office 365、Microsoft Defender for Office 365、office 365 評価、try office 365、Microsoft Defender、Microsoft Defender for Endpoint
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0f5d82e9baaca7209f8a91a7f1984aa38e3102e6
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63681746"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 を評価する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Microsoft Defender for Office 365評価はパブリック プレビュー中です。 このプレビュー バージョンは、サービス レベル契約なしで提供されます。 一部の機能はサポートされないか、機能が制限される可能性があります。

セキュリティ製品の徹底的な評価を実施すると、アップグレードと購入に関する情報に基づいた意思決定を行う際に役立ちます。 セキュリティ製品の機能を試して、セキュリティ運用チームの日常業務に役立つ方法を評価するのに役立ちます。

[Microsoft Defender for Office 365](defender-for-office-365.md) 評価エクスペリエンスは、デバイスと環境構成の複雑さを排除し、Microsoft Defender for Office 365 の機能の評価に集中できるよう設計されています。 評価モードでは、MX レコードを Microsoft にExchange Onlineせずに、メールボックスに送信されるメッセージはすべて評価できます。 この機能は電子メール保護にのみ適用され、Word、Office、またはクライアントのようなクライアントSharePoint適用Teams。

microsoft Defender for Office 365 をサポートするライセンスをまだ持ってない場合は、[無料の 30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) 日間の評価を開始し、Microsoft 365 Defender ポータルの機能をテストできます<https://security.microsoft.com>。 クイック セットアップを楽しめ、必要に応じて簡単にオフにできます。

> [!NOTE]
> Microsoft 365 Defender <https://security.microsoft.com>ポータルにアクセスしている場合は、「その他」セクションの 「メール **&** \> Collaboration **Policies & Rules** \> **Threat Policies** \> Evaluation mode」で、Office 365 評価用の Defender を **開始** できます。 または、[評価モード] ページに直接 **移動するには** 、 を使用します <https://security.microsoft.com/atpEvaluation>。

## <a name="how-the-evaluation-works"></a>評価のしくみ

評価モードOffice 365 Defender は、マルウェアなどのOffice 365をログに記録するが、メッセージに対して動作しない電子メール ポリシー用の Defender を作成します。 MX レコードの構成を変更する必要はありません。

評価モードでは、[セーフポリシー](safe-attachments.md)セーフ[添付](safe-links.md)ファイル、セーフ、メールボックス インテリジェンスが[](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)設定されます。 すべての Defender for Office 365ポリシーは、バックグラウンドで強制不可モードで作成され、表示されません。

セットアップの一環として、評価モードではコネクタの [拡張](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) フィルター (スキップ リストとも呼ばれる) _も構成されます_。 この構成では、IP アドレスと送信者情報を保持することでフィルターの精度が向上します。それ以外の場合、メールが Defender for Office 365 の前にあるメール セキュリティ ゲートウェイ (ESG) を通過すると失われます。 また、コネクタのフィルター機能が強化され、既存のスパム対策 (EOP) Exchange Online Protectionフィッシング対策ポリシーのフィルタリング精度も向上します。

コネクタのフィルター処理が強化された場合、フィルターの精度が向上しますが、Office 365 用の Defender の前に ESG を持ち、現在 EOP フィルター処理をバイパスしない場合は、特定のメッセージの配信可能性が変わる可能性があります。 影響は EOP ポリシーに制限されます。評価のOffice 365設定されたポリシーの Defender は、強制以外のモードで作成されます。 潜在的な運用への影響を最小限に抑えるために、メール フロー ルール (トランスポート ルールとも呼ばれる) を作成して、メッセージのスパム信頼レベル (SCL) を -1 に設定することで、ほとんどの EOP フィルターをバイパスできます。 詳細[については、「メール フロー ルールを使用して、](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)メッセージ内のスパム信頼レベル (SCL) を設定するExchange Online参照してください。

評価モードを設定すると、ポリシーが実装された場合にブロックされたメッセージを定量化する最大 90 日間のデータを含む日次レポートがあります (たとえば、削除、迷惑メールへの送信、検疫など)。 レポートは、すべての Defender に対して、Office 365 EOP 検出用に生成されます。 レポートは検出テクノロジ (偽装など) ごとに集計され、時間範囲でフィルター処理できます。 さらに、メッセージ レポートをオンデマンドで作成してカスタム ピボットを作成したり、エクスプローラーを使用して詳細なメッセージを作成することもできます。

簡略化されたセットアップ エクスペリエンスを使用すると、次の作業に集中できます。

- 評価の実行
- 詳細なレポートの取得
- アクションのレポートの分析
- 評価結果の提示

## <a name="before-you-begin"></a>はじめに

### <a name="licensing"></a>ライセンス

評価にアクセスするには、ライセンス要件を満たす必要があります。 次のライセンスが動作します。

- Microsoft Defender for Office 365 プラン 1
- Microsoft Defender for Office 365 プラン 2
- Microsoft 365 E5、Microsoft 365 E5 Security
- Office 365 E5

これらのライセンスを 1 つも持ってない場合は、試用版ライセンスを取得する必要があります。

#### <a name="trial"></a>試用版

Microsoft Defender for microsoft Defender for Office 365するには、課金管理者ロールまたはグローバル管理者ロール **が必要です**。 グローバル管理者の役割を持つユーザーにアクセス許可を要求します。 [サブスクリプションとライセンスの詳細](../../commerce/licenses/subscriptions-and-licenses.md)

適切な役割を果たしたら、Microsoft 365 管理センター で Microsoft Defender for Office 365 (プラン 2) の試用版ライセンスを取得し、課金サービスに移動し、microsoft Defender for Office 365 (プラン 2) <https://admin.microsoft.com>  \> 試用版を見つけて選択します。 または、試用版ページに直接移動するには <https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)> 、試用版には 25 ライセンスの 30 日間の無料試用版が含まれています。

高度な脅威を監視および報告する評価を含む 30 日間のウィンドウがあります。 また、完全な Defender を有効な機能に使用する場合は、有料サブスクリプションを購入Office 365があります。

### <a name="roles"></a>役割

**Exchange Online評価モードで** Defender を設定するには、Office 365ロールが必要です。 コンプライアンスまたはMicrosoft 365管理者の役割を割り当てると機能しません。

- [アクセス許可の詳細については、Exchange Online](/exchange/permissions-exo/permissions-exo)
- [管理者ロールの割り当てについて](../../admin/add-users/assign-admin-roles.md)

次の役割が必要です。

|タスク|ロール (Exchange Online)|
|---|---|
|無料試用版を取得するか、Microsoft Defender for Office 365購入する (プラン 2)|課金管理者ロールまたはグローバル管理者ロール|
|評価ポリシーの作成|リモートドメインと受け入れドメインの役割。セキュリティ管理者の役割|
|評価ポリシーの編集|リモートドメインと受け入れドメインの役割。セキュリティ管理者の役割|
|評価ポリシーの削除|リモートドメインと受け入れドメインの役割。セキュリティ管理者の役割 |
|評価レポートの表示|セキュリティ管理者の役割またはセキュリティ 閲覧者の役割|

### <a name="enhanced-filtering-for-connectors"></a>コネクタのフィルター処理の強化

バルクExchange Online Protectionスパム保護など、ユーザーのポリシーは同じままです。 ただし、この評価ではコネクタの拡張フィルター処理がオンにされ、バイパスしない限り、メール フローとポリシー Exchange Online Protection影響を与える可能性があります。

コネクタの拡張フィルターを使用すると、テナントはスプーフィング防止保護を使用できます。 コネクタの拡張フィルターを有効にせずにメール セキュリティ ゲートウェイ (ESG) を使用している場合、スプーフィング対策はサポートされません。

### <a name="urls"></a>URL

URL はメール フロー中にデトナ処理されます。 特定の URL を削除しない場合は、許可された URL のリストを適切に管理します。 詳細については [、「テナント許可/ブロック一覧の管理」](tenant-allow-block-list.md) を参照してください。

電子メール メッセージのボディ内の URL リンクは折り返されません。顧客への影響を減らします。

### <a name="email-routing"></a>メールのルーティング

メールをルーティングする受信コネクタの名前など、メールの現在のルーティング方法を設定する必要がある対応する詳細を準備します。 アプリケーションを使用しているExchange Online Protectionコネクタは使用しない場合があります。 [メール フローとメール ルーティングの詳細](/office365/servicedescriptions/exchange-online-service-description/mail-flow)

サポートされる電子メール ルーティングシナリオは次のとおりです。

- **サード パーティ** のパートナーまたはオンプレミス のサービス プロバイダー: 評価する受信コネクタは、サード パーティプロバイダーを使用するか、オンプレミスの電子メール セキュリティ用のソリューションを使用しています。
- **Microsoft Exchange Online保護のみ**: 評価するテナントは、Office 365 を電子メール セキュリティに使用し、メール Exchange (MX) レコードは Microsoft をポイントします。

### <a name="email-security-gateway"></a>メール セキュリティ ゲートウェイ

サードパーティの電子メール セキュリティ ゲートウェイ (ESG) を使用している場合は、プロバイダーの名前を知る必要があります。 オンプレミスの ESG またはサポートされていないベンダーを使用している場合は、デバイスのパブリック IP アドレスを知る必要があります。

サポートされているサード パーティパートナーには、次のものが含まれます。

- バラクーダ
- IronPort
- Mimecast
- Proofpoint
- Sophos
- Symantec
- Trend Micro

### <a name="scoping"></a>スコープ

評価の範囲を受信コネクタに設定できます。 コネクタが構成されていない場合、評価スコープを使用すると、管理者はテナント内の任意のユーザーからデータを収集して、Defender のデータをOffice 365。

## <a name="get-started-with-the-evaluation"></a>評価の開始

次のアクセス ポイントから、Office 365ポータルで Microsoft Defender の評価セットアップ Microsoft 365 Defenderを検索します。

-  \>エンドポイント **脆弱性の管理** \>**ダッシュボード** (<https://security.microsoft.com/tvm_dashboard>)
- **メール&コラボレーション** \>**ポリシー&ルール** \>**脅威ポリシー** (<https://security.microsoft.com/threatpolicy>)
- **レポート** \>**メール&コラボレーション** \>**メール&コラボレーション レポート** (<https://security.microsoft.com/emailandcollabreport>)

## <a name="setting-up-the-evaluation"></a>評価の設定

評価のセットアップ フローを開始すると、2 つのルーティング オプションが提供されます。 組織のメール ルーティングのセットアップと評価のニーズに応じて、サードパーティのサービス プロバイダーまたはオンプレミス サービス プロバイダーを使用しているか、または Microsoft Exchange Online のみを使用しているかを選択できます。

- サード パーティのパートナーやオンプレミス のサービス プロバイダーを使用している場合は、ドロップダウン メニューからベンダーの名前を選択する必要があります。 その他のコネクター関連の詳細を入力します。

- MX **レコードMicrosoft Exchange Online** Microsoft をポイントし、ユーザーがメールボックスを持っている場合は、[Exchange Online] を選択します。

必要に応じて設定を確認し、編集します。 次に、[評価の **作成] を選択します**。 セットアップが完了したという確認メッセージが表示されます。

評価レポートの Microsoft Defender Office 365は、1 日に 1 回生成されます。 データの入力に最大で 24 時間かかる場合があります。

### <a name="exchange-mail-flow-rules-optional"></a>Exchange フロー ルール (オプション)

既存のゲートウェイがある場合は、評価モードを有効にすると、コネクタの拡張フィルター処理がアクティブになります。 この機能は、受信送信者の IP アドレスを変更することで、フィルターの精度を向上します。 この機能はフィルターの評決を変更する可能性があります。また、フィルターをバイパスしない場合は、Exchange Online Protectionメッセージの配信可能性が変わる可能性があります。 この場合、影響を分析するためにフィルター処理を一時的にバイパスする必要があります。 フィルター処理をバイパスするには、メッセージの SCL を -1 に設定する Exchange 管理センター (EAC) にメール フロー ルール (トランスポート ルールとも呼ばれる) を作成します (まだメッセージが存在しない場合)。<https://admin.exchange.microsoft.com/#/transportrules> 手順については、「メール フロー ルールを使用して、メッセージ内のスパム信頼レベル [(SCL) を設定する」を参照](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)Exchange Online。

## <a name="evaluate-capabilities"></a>機能を評価する

評価レポートが生成された後、組織内の電子メールとコラボレーション ワークスペースで、高度な脅威リンク、高度な脅威の添付ファイル、および潜在的な偽装が識別された数を確認します。

試用版の有効期限が切れたら、レポートに引き続き 90 日間アクセスできます。 ただし、それ以上の情報は収集しない。 試用版の有効期限が切れた後に microsoft Defender for Office 365 を引き続き使用する場合は、[Microsoft Defender for Office 365 (プラン 2) の有料サブスクリプションを購入してください](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)。

[ルーティング **の更新設定**、評価をいつでもオフにできます。 ただし、無効にした後で評価を続行する場合は、同じセットアップ プロセスを再度実行する必要があります。

## <a name="provide-feedback"></a>フィードバックの提供

フィードバックは、高度な攻撃から環境を保護する上で役立ちます。 製品機能と評価結果のエクスペリエンスと印象を共有します。

[ **フィードバックを提供する]** を選択して、ご意見をお寄せください。
