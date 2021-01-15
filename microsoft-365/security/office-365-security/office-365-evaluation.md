---
title: Microsoft Defender を 365 Office評価する
description: 評価モードOffice 365 用の Defender は、マルウェアなどの評価を記録するが、メッセージには作用しない Office 365 電子メール ポリシー用の Defender を作成します。
keywords: evaluate Office 365, Microsoft Defender for Office 365, office 365 evaluation, try office 365, Microsoft Defender, ATP
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f8f105215b23ec49318c133714e758e2a2a9c1df
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870923"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Microsoft Defender を 365 Office評価する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Microsoft Defender for Office 365 評価版はパブリック プレビュー中です。 このプレビュー バージョンは、サービス レベルアグリーメントなしで提供されます。 一部の機能がサポートされていないか、機能が制限されている可能性があります。

包括的なセキュリティ製品評価を実施すると、アップグレードと購入に関する情報に基づいた意思決定を行うのに役立ちます。 セキュリティ製品の機能を試して、セキュリティ運用チームが日常業務に役立つ方法を評価するのに役立ちます。

[Microsoft Defender for Office 365](office-365-atp.md)の評価エクスペリエンスは、セキュリティ ソリューションの機能の評価に集中できるよう、デバイスと環境の構成の複雑さを排除するように設計されています。 これは電子メール保護にのみ適用され、SharePoint、Office Teams には適用されません。

microsoft Defender for Office 365 をサポートするライセンスをまだお持ちでない場合は、無料の [30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) 日間の評価を開始し、Office 365 セキュリティ & コンプライアンス センター https://protection.office.com/homepage) (. 迅速なセットアップが楽しめ、必要に応じて簡単にオフにできます。

## <a name="how-the-evaluation-works"></a>評価のしくみ

評価モードOffice 365 用の Defender は、マルウェアなどの評価を記録するが、メッセージには作用しない Office 365 電子メール ポリシー用の Defender を作成します。 MX レコード構成を変更する必要はありません。

評価モードでは、 [安全な添付ファイル](atp-safe-attachments.md)、安全な [](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) [リンク](atp-safe-links.md)、フィッシング詐欺対策の偽装ポリシーがユーザーに代わって設定されます。 365 Office用のすべての Defender は、バックグラウンドで非強制モードで作成され、表示されません。

セットアップの一環として、評価モードではコネクタの [拡張フィルターも構成されます](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。 IP アドレスと送信者情報を保持することでフィルターの精度が向上します。それ以外の場合、メールが Office 365 の Defender の前にある電子メール セキュリティ ゲートウェイ (DEFENDER) を通過すると失われます。 拡張フィルタリングは、Exchange Online Protection (EOP) のスパム対策およびフィッシング対策ポリシーのフィルタリング精度も向上します。

一部のサポートされていないシナリオに対する潜在的な運用への影響を最小限に抑えるために、Spam Confidence Level (SCL) を -1 に設定するトランスポート ルールを作成することで、すべての EOP フィルタリングをバイパスできます。 詳細 [については、「EAC を使用して、メッセージの SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)を設定するメール フロー ルールを作成する」   を参照してください。

評価モードを設定すると、ポリシーが実装された場合にブロックされるメッセージを数値化する最大 90 日間のデータ (削除、迷惑メールへの送信、検疫など) で毎日レポートが更新されます。 レポートは、365 および EOP の検出Office Defender すべてについて生成されます。 これらは検出テクノロジ (偽装など) ごとに集計され、時間範囲でフィルター処理できます。 さらに、カスタム ピボットを作成したり、脅威エクスプローラーを使用して詳細なメッセージを作成したりするために、メッセージ レポートをオンデマンドで作成できます。

簡素化されたセットアップ エクスペリエンスを使用すると、次の作業に集中できます。

- 評価の実行
- 詳細レポートの取得
- アクションに関するレポートの分析
- 評価結果の提示

## <a name="before-you-begin"></a>開始する前に

### <a name="licensing"></a>ライセンス

評価にアクセスするには、ライセンス要件を満たす必要があります。 次のライセンスが機能します。

- Microsoft Defender for Office 365 プラン 1
- Microsoft Defender for Office 365 プラン 2
- Microsoft 365 E5、Microsoft 365 E5 Security
- Office 365 E5

これらのライセンスが 1 つも持たなかった場合は、試用版ライセンスを取得する必要があります。

#### <a name="trial"></a>試用版

Office 365 用の Microsoft Defender の試用版ライセンスを取得するには、課金管理者の役割またはグローバル管理者の役割 **が必要です**。 グローバル管理者ロールを持つユーザーにアクセス許可を要求します。 [サブスクリプションとライセンスについて](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

適切なロールを取得したら、課金サービス > に移動して、Microsoft 365 管理センターで Office 365 (プラン 2) 用の Microsoft Defender の試用版ライセンスを取得します。 試用版には、25 ライセンスの 30 日間の無料試用版が含まれています。 [microsoft Defender for Office 365 (プラン 2) の試用版を取得します](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)。

高度な脅威を監視および報告する評価を含む 30 日間のウィンドウがあります。 また、365 の機能に対する完全な Defender を使用する場合は、有料サブスクリプションをOfficeすることもできます。

### <a name="roles"></a>Roles

Exchange Online の役割は、評価モードで 365 Office Defender をセットアップする必要があります。

- [Exchange Online のアクセス許可について](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
- [管理者ロールの割り当てについて](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)

次の役割が必要です。

|Task|Role|
|---|---|
|無料試用版を取得するか、Microsoft Defender を Office 365 用に購入する (プラン 2)|課金管理者ロールまたはグローバル管理者ロール|
|評価ポリシーを作成する|"Remote and Accepted Domains/リモートドメインと受け入れドメイン" 役割セキュリティ管理者ロール|
|評価ポリシーの編集|"Remote and Accepted Domains/リモートドメインと受け入れドメイン" 役割セキュリティ管理者ロール|
|評価ポリシーを削除する|"Remote and Accepted Domains/リモートドメインと受け入れドメイン" 役割セキュリティ管理者ロール |
|評価レポートの表示|セキュリティ管理者ロールまたはセキュリティ閲覧者ロール|
|


### <a name="enhanced-filtering"></a>拡張フィルタリング

一括保護やスパム保護などの Exchange Online Protection ポリシーは変わりません。 メッセージ配信も同じままです。 ただし、この評価ではコネクタの拡張フィルター処理が有効にされ、バイパスされていない限り、メール フローと Exchange Online Protection ポリシーに影響します。

コネクタのフィルター処理が強化され、テナントはスプーフィング対策保護を使用できます。 コネクタの拡張フィルタリングを有効にせずに電子メール セキュリティ ゲートウェイ (RF) を使用している場合、スプーフィング対策はサポートされません。

### <a name="urls"></a>URL

URL はメール フロー中にデトニトされます。 特定の URL を分析しない場合は、許可されている URL の一覧を適切に管理します。 詳細 [については、「テナントの許可/ブロックリストの URL](tenant-allow-block-list.md) の管理」を参照してください。

電子メール メッセージのボディ内の URL リンクは折り返されません。お客様への影響を減らします。

### <a name="email-routing"></a>電子メールルーティング

メールをルーティングする受信コネクタの名前など、メールの現在のルーティング方法を設定するために必要な対応する詳細を準備します。 Exchange Online Protection を使用しているだけの場合は、コネクタを使用する必要があります。 [メール フローと電子メール ルーティングの詳細](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)

サポートされる電子メール ルーティング シナリオは次のとおりです。

- **サード パーティ** のパートナーまたはオンプレミスのサービス プロバイダー: 評価する受信コネクタは、サード パーティプロバイダーを使用するか、オンプレミスの電子メール セキュリティのソリューションを使用しています。
- **Microsoft Exchange Online保護** のみ: 評価するテナントは Office 365 を電子メール セキュリティに使用し、Mail Exchange (MX) レコードは Microsoft をポイントします。

### <a name="email-security-gateway"></a>電子メール セキュリティ ゲートウェイ

サード パーティの電子メール セキュリティ ゲートウェイ (KM) を使用している場合は、プロバイダーの名前を知っている必要があります。 オンプレミスベンダーまたはサポートされていないベンダーで、オンプレミスまたはサポートされていないベンダーを使用している場合は、デバイスのパブリック IP アドレスを知っている必要があります。

サポートされているサード パーティパートナーには、次のものがあります。

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- 最も近い
- Symantec
- Trend Micro

### <a name="scoping"></a>スコープ

評価の範囲を受信コネクタに設定できます。 コネクタが構成されていない場合、評価スコープを使用すると、管理者はテナント内の任意のユーザーからデータを収集し、365 用に Defender を評価Officeできます。

## <a name="get-started-with-the-evaluation"></a>評価の開始

Office 365 セキュリティ & コンプライアンス センター (3 つのアクセス ポイントから) で、Office 365 評価用の Microsoft Office Defender & セットアップ カードを https://protection.office.com/homepage) 検索します。

- 脅威管理> ダッシュボード
- 脅威管理>ポリシー
- レポート> ダッシュボード

## <a name="setting-up-the-evaluation"></a>評価の設定

評価のセットアップ フローを開始すると、2 つのルーティング オプションが提供されます。 組織のメール ルーティングのセットアップと評価のニーズに応じて、サードパーティまたはオンプレミスのサービス プロバイダーを使用しているか、または Microsoft Exchange Online のみを使用しているかを選択できます。

- サードパーティのパートナーやオンプレミスのサービス プロバイダーを使用している場合は、ドロップダウン メニューからベンダーの名前を選択する必要があります。 その他のコネクタ関連の詳細を指定します。

- MX Microsoft Exchange Online Microsoft をポイントし、Exchange Online メールボックスを持っている場合は、このオプションを選択します。

設定を確認し、必要に応じて編集します。 次に、[評価の **作成] を選択します**。 セットアップが完了したかどうかを示す確認メッセージが表示されます。

Microsoft Defender for Office 365 評価レポートは、1 日に 1 回生成されます。 データが入力されるには、最大 24 時間かかる場合があります。

### <a name="exchange-rules-optional"></a>Exchange ルール (オプション)

既存のゲートウェイがある場合は、コネクタの拡張フィルター処理がアクティブ化され、受信送信者の IP アドレスが変更されるので、フィルター処理をバイパスできます。 バイパスするには、Exchange 管理センターに移動し、SCL -1 のポリシーを作成します (まだポリシーを持ってない場合)。 ルール コンポーネントの詳細と動作方法については、Exchange Online のメール フロー ルール (トランスポート ルール) を参照してください。

## <a name="evaluate-capabilities"></a>機能を評価する

評価レポートが生成された後、組織内の電子メールとコラボレーション ワークスペースで、高度な脅威リンク、高度な脅威の添付ファイル、および潜在的な偽装が識別された数を確認します。

試用版の有効期限が切れた後、90 日間レポートに引き続きアクセスできます。 ただし、それ以上の情報は収集されます。 試用版の有効期限が切れた後に Office 365 の Microsoft Defender を引き続き使用する場合は [、microsoft Defender for Office 365 (プラン 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)の有料サブスクリプションを購入してください。

[設定] **に移動** してルーティングを更新したり、評価をいつでもオフにできます。 ただし、無効にした後で評価を続行する場合は、同じセットアップ プロセスを再度実行する必要があります。

## <a name="provide-feedback"></a>フィードバックの提供

お客様からのフィードバックは、高度な攻撃から環境を保護する上で役立ちます。 製品の機能と評価結果のエクスペリエンスと印象を共有します。

フィードバック **を送信するを** 選択して、ご意見をお聞かせください。
