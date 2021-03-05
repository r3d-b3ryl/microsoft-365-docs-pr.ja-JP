---
title: Microsoft Defender を 365 のOfficeする
description: 評価モードOffice 365 の Defender は、マルウェアなどの評決をログに記録するが、メッセージに対して動作しない Office 365 メール ポリシーの Defender を作成します。
keywords: 評価Office 365、Microsoft Defender for Office 365、office 365 評価、try office 365、Microsoft Defender、ATP
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1a9bf9461e8cf6d62e4283c9112b801371242f2e
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453707"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Microsoft Defender を 365 のOfficeする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Microsoft Defender for Office 365 評価はパブリック プレビュー中です。 このプレビュー バージョンは、サービス レベル契約なしで提供されます。 一部の機能はサポートされていないか、制限された機能を持っている可能性があります。

包括的なセキュリティ製品評価を実施すると、アップグレードと購入に関する情報に基づいた意思決定を行う際に役立ちます。 セキュリティ製品の機能を試して、セキュリティ運用チームの日常業務に役立つ方法を評価するのに役立ちます。

[Microsoft Defender for Office 365](office-365-atp.md)評価エクスペリエンスは、セキュリティ ソリューションの機能の評価に集中できるよう、デバイスと環境構成の複雑さを排除するように設計されています。 これは、メール保護にのみ適用され、SharePoint、Word、Teams Officeクライアントに適用されません。

microsoft Defender for Office 365 をサポートするライセンスをまだ持ってない場合は、無料[の 30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)日間の評価を開始し、Office 365 セキュリティ & コンプライアンス センター () で機能をテストできます。 https://protection.office.com/homepage) クイック セットアップを楽しめ、必要に応じて簡単にオフにできます。

## <a name="how-the-evaluation-works"></a>評価のしくみ

評価モードOffice 365 の Defender は、マルウェアなどの評決をログに記録するが、メッセージに対して動作しない Office 365 メール ポリシーの Defender を作成します。 MX レコードの構成を変更する必要はありません。

評価モードでは、 [安全な添付](atp-safe-attachments.md)ファイル [、安全な](atp-safe-links.md)リンク、メールボックス [インテリジェンス](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) ベースの偽装ポリシーが代理で設定されます。 すべての Defender for Office 365 ポリシーはバックグラウンドで強制不可モードで作成され、表示されません。

セットアップの一環として、評価モードではコネクタの [拡張フィルターも構成します](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。 IP アドレスと送信者情報を保持することでフィルターの精度が向上します。それ以外の場合、メールが Defender 365 の Defender の前にあるメール セキュリティ ゲートウェイ (ESG) を通過すると失われますOffice。 また、コネクタのフィルター処理が強化され、既存の Exchange Online Protection (EOP) スパム対策ポリシーおよびフィッシング対策ポリシーのフィルタリング精度も向上します。

コネクタの拡張フィルター処理を有効にすると、フィルターの精度が向上しますが、Office 365 の Defender の前に ESG が設定され、現在 EOP フィルター処理をバイパスしていない場合は、特定のメッセージの配信可能性が変わる可能性があります。 影響は EOP ポリシーに制限されます。評価の一部としてセットアップされる MDO ポリシーは、強制以外のモードで作成されます。 潜在的な運用への影響を最小限に抑えるために、トランスポート ルールを作成してスパム信頼レベル (SCL) を -1 に設定することで、すべての EOP フィルターをバイパスできます。 詳細 [については、「EAC を使用してメッセージの SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)を設定するメール フロー ルールを作成する」   を参照してください。

評価モードが設定されている場合、ポリシーが実装された場合にブロックされたメッセージを定量化する最大 90 日間のデータを含むレポートが毎日更新されます (たとえば、削除、迷惑メールへの送信、検疫など)。 レポートは、365 および EOP 検出Office Defender に対して生成されます。 これらは検出テクノロジ (偽装など) ごとに集計され、時間範囲でフィルター処理できます。 さらに、メッセージ レポートをオンデマンドで作成して、カスタム ピボットを作成したり、Threat Explorer を使用して詳細なメッセージを作成することもできます。

セットアップの簡略化により、次の作業に集中できます。

- 評価の実行
- 詳細なレポートの取得
- アクションのレポートの分析
- 評価結果の提示

## <a name="before-you-begin"></a>はじめに

### <a name="licensing"></a>ライセンス

評価にアクセスするには、ライセンス要件を満たす必要があります。 次のライセンスが動作します。

- Microsoft Defender for Office 365 プラン 1
- Microsoft Defender for Office 365 プラン 2
- Microsoft 365 E5、Microsoft 365 E5 セキュリティ
- Office 365 E5

これらのライセンスを 1 つも持ってない場合は、試用版ライセンスを取得する必要があります。

#### <a name="trial"></a>試用版

Microsoft Defender for Office 365 の試用版ライセンスを取得するには、課金管理者の役割またはグローバル管理者の役割 **を持っている必要があります**。 グローバル管理者の役割を持つユーザーにアクセス許可を要求します。 [サブスクリプションとライセンスの詳細](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

適切な役割を果たしたら、Microsoft 365 管理センターの Microsoft Defender for Office 365 (プラン 2) の試用版ライセンスを請求 > 購入サービスに移動して入手してください。 試用版には、25 ライセンスの 30 日間の無料試用版が含まれています。 [Microsoft Defender for Office 365 (プラン 2) を取得します](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)。

高度な脅威を監視および報告する評価を含む 30 日間のウィンドウがあります。 また、365 の機能に対する完全な Defender が必要な場合は、有料サブスクリプションOfficeがあります。

### <a name="roles"></a>Roles

Exchange Online の役割は、評価モードで 365 Office Defender をセットアップするために必要です。

- [Exchange Online のアクセス許可の詳細](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
- [管理者ロールの割り当てについて](../../admin/add-users/assign-admin-roles.md)

次の役割が必要です。

|Task|役割|
|---|---|
|無料試用版を取得するか、Microsoft Defender for Office 365 (プラン 2)|課金管理者ロールまたはグローバル管理者ロール|
|評価ポリシーの作成|リモートドメインと受け入れドメインの役割。セキュリティ管理者の役割|
|評価ポリシーの編集|リモートドメインと受け入れドメインの役割。セキュリティ管理者の役割|
|評価ポリシーの削除|リモートドメインと受け入れドメインの役割。セキュリティ管理者の役割 |
|評価レポートの表示|セキュリティ管理者の役割またはセキュリティ 閲覧者の役割|
|


### <a name="enhanced-filtering"></a>拡張フィルター

バルク保護やスパム保護など、Exchange Online Protection ポリシーは同じままです。 ただし、この評価ではコネクタの拡張フィルター処理が有効にされ、バイパスされていない限り、メール フローと Exchange Online Protection ポリシーに影響を与える可能性があります。

コネクタのフィルター処理が強化され、テナントはスプーフィング防止保護を使用できます。 コネクタの拡張フィルターを有効にせずにメール セキュリティ ゲートウェイ (ESG) を使用している場合、スプーフィング対策はサポートされません。

### <a name="urls"></a>URL

URL はメール フロー中にデトナ処理されます。 特定の URL を削除しない場合は、許可された URL のリストを適切に管理します。 詳細については [、「テナント許可/ブロック一覧の管理」](tenant-allow-block-list.md) を参照してください。

電子メール メッセージのボディ内の URL リンクは折り返されません。顧客への影響を減らします。

### <a name="email-routing"></a>メールのルーティング

メールをルーティングする受信コネクタの名前など、メールの現在のルーティング方法を設定する必要がある対応する詳細を準備します。 Exchange Online Protection を使用しているだけの場合は、コネクタを持つ必要があります。 [メール フローとメール ルーティングの詳細](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)

サポートされる電子メール ルーティングシナリオは次のとおりです。

- **サード パーティパートナー** またはオンプレミス サービス プロバイダー : 評価する受信コネクタは、サード パーティプロバイダーを使用するか、オンプレミスの電子メール セキュリティ用のソリューションを使用しています。
- **Microsoft Exchange Online保護** のみ: 評価するテナントは、Office 365 を電子メール セキュリティに使用し、メール Exchange (MX) レコードは Microsoft をポイントします。

### <a name="email-security-gateway"></a>メール セキュリティ ゲートウェイ

サードパーティの電子メール セキュリティ ゲートウェイ (ESG) を使用している場合は、プロバイダーの名前を知る必要があります。 ESG オンプレミスベンダーまたはサポートされていないベンダーを使用している場合は、デバイスのパブリック IP アドレスを知る必要があります。

サポートされているサード パーティパートナーには、次のものが含まれます。

- バラクーダ
- IronPort
- Mimecast
- Proofpoint
- Sophos
- シマンテック
- Trend Micro

### <a name="scoping"></a>スコープ

評価の範囲を受信コネクタに指定できます。 コネクタが構成されていない場合、評価スコープを使用すると、管理者はテナント内の任意のユーザーからデータを収集して、365 の Defender を評価Officeできます。

## <a name="get-started-with-the-evaluation"></a>評価の開始

Office 365 セキュリティ & コンプライアンス センター (3 つのアクセス ポイントから) で、Microsoft Defender for Office 365 評価セットアップ カードを https://protection.office.com/homepage) 検索します。

- 脅威管理>ダッシュボード
- 脅威管理>ポリシー
- レポート > ダッシュボード

## <a name="setting-up-the-evaluation"></a>評価のセットアップ

評価のセットアップ フローを開始すると、2 つのルーティング オプションが提供されます。 組織のメール ルーティングのセットアップと評価のニーズに応じて、サードパーティサービス プロバイダーまたはオンプレミス サービス プロバイダーを使用しているか、または Microsoft Exchange Online のみを使用しているかを選択できます。

- サード パーティのパートナーまたはオンプレミス サービス プロバイダーを使用している場合は、ドロップダウン メニューからベンダーの名前を選択する必要があります。 他のコネクタ関連の詳細を指定します。

- MX レコードMicrosoft Exchange Online Microsoft をポイントし、Exchange Online メールボックスを持っている場合は、[ユーザー設定] を選択します。

必要に応じて設定を確認し、編集します。 次に、[評価の **作成] を選択します**。 セットアップが完了したという確認メッセージが表示されます。

Microsoft Defender for Office 365 評価レポートは、1 日に 1 回生成されます。 データの入力に最大で 24 時間かかる場合があります。

### <a name="exchange-rules-optional"></a>Exchange ルール (オプション)

既存のゲートウェイがある場合は、評価モードを有効にすると、コネクタの拡張フィルター処理がアクティブになります。 これにより、受信送信者の IP アドレスを変更することで、フィルターの精度が向上します。 これにより、フィルターの評決が変更される可能性があります。また、Exchange Online Protection をバイパスしていない場合は、特定のメッセージの配信可能性が変わる可能性があります。 この場合、影響を分析するためにフィルター処理を一時的にバイパスする必要があります。 バイパスするには、Exchange 管理センターに移動し、SCL -1 のポリシーを作成します (まだポリシーを持ってない場合)。 ルール コンポーネントの詳細と動作方法については、「Exchange Online のメール フロー ルール (トランスポート ルール)」を参照してください。

## <a name="evaluate-capabilities"></a>機能を評価する

評価レポートが生成された後、組織内の電子メールとコラボレーション ワークスペースで、高度な脅威リンク、高度な脅威の添付ファイル、および潜在的な偽装が識別された数を確認します。

試用版の有効期限が切れたら、レポートに引き続き 90 日間アクセスできます。 ただし、それ以上の情報は収集しない。 試用版の有効期限が切れた後に microsoft Defender for Office 365 を引き続き使用する場合は、microsoft Defender for [Office 365 (プラン 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)の有料サブスクリプションを購入してください。

[設定] に移動 **して** ルーティングを更新したり、評価をいつでもオフにできます。 ただし、無効にした後で評価を続行する場合は、同じセットアップ プロセスを再度実行する必要があります。

## <a name="provide-feedback"></a>フィードバックの提供

フィードバックは、高度な攻撃から環境を保護する上で役立ちます。 製品機能と評価結果のエクスペリエンスと印象を共有します。

[ **フィードバックを提供する]** を選択して、ご意見をお寄せください。
