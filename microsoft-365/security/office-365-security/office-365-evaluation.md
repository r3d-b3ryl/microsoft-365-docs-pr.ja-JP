---
title: Microsoft Defender for Office 365 を評価する
description: 評価モードのDefender for Office 365は、マルウェアなどの判定を記録するDefender for Office 365電子メール ポリシーを作成しますが、メッセージには作用しません。
keywords: Office 365の評価、Microsoft Defender for Office 365、office 365 の評価、office 365、Microsoft Defender、Microsoft Defender for Endpointを試す
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
ms.sourcegitcommit: 74518b920b4166adccc10ea1581a62c44bb14edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2022
ms.locfileid: "66993756"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 を評価する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Microsoft Defender for Office 365評価はパブリック プレビュー段階です。 このプレビュー バージョンは、サービス レベル アグリーメントなしで提供されます。 一部の機能はサポートされないか、機能が制限される可能性があります。

徹底的なセキュリティ製品評価を実施すると、アップグレードと購入に関する情報に基づいた意思決定を行うことができます。 セキュリティ製品の機能を試して、セキュリティ運用チームが日常のタスクにどのように役立つかを評価するのに役立ちます。

[Microsoft Defender for Office 365](defender-for-office-365.md)評価エクスペリエンスは、デバイスと環境の構成の複雑さを排除し、Microsoft Defender for Office 365の機能の評価に集中できるように設計されています。 評価モードでは、Exchange Online メールボックスに送信されたすべてのメッセージを、MX レコードを Microsoft にポイントすることなく評価できます。 この機能はメール保護にのみ適用され、Word、SharePoint、Teams などの Office クライアントには適用されません。

Microsoft Defender for Office 365をサポートするライセンスをまだ持っていない場合は、[無料の 30 日間の評価](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)を開始し、Microsoft 365 Defender ポータルで<https://security.microsoft.com>機能をテストできます。 簡単なセットアップが可能で、必要に応じて簡単にオフにすることができます。

> [!NOTE]
> Microsoft 365 Defender ポータルの場合は、[**その他**] セクションの <https://security.microsoft.com>[コラボレーション \> ポリシー&ルール\>**脅威ポリシー** \> **の評価モード****をEmail &** する] で **Defender for Office 365** 評価を開始できます。 または、 **評価モード** ページに直接移動するには、 <https://security.microsoft.com/atpEvaluation>.

## <a name="how-the-evaluation-works"></a>評価のしくみ

評価モードのDefender for Office 365は、マルウェアなどの判定を記録するDefender for Office 365電子メール ポリシーを作成しますが、メッセージには作用しません。 MX レコードの構成を変更する必要はありません。

評価モードでは、無効ポリシーの [安全な添付ファイル](safe-attachments.md)、 [安全なリンク](safe-links.md)、 [メールボックス インテリジェンス](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) がユーザーに代わって設定されます。 すべてのDefender for Office 365 ポリシーは、バックグラウンドで非適用モードで作成され、自分には表示されません。

セットアップの一環として、評価モードでは [、コネクタの拡張フィルター処理](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) ( _リストのスキップ_ とも呼ばれます) も構成されます。 この構成では、IP アドレスと送信者の情報を保持することでフィルター処理の精度が向上します。それ以外の場合は、メールがDefender for Office 365の前で電子メール セキュリティ ゲートウェイ (ESG) を通過すると失われます。 コネクタのフィルター処理の強化により、既存のExchange Online Protection (EOP) スパム対策およびフィッシング対策ポリシーのフィルター処理の精度も向上します。

コネクタのフィルター処理を強化すると、フィルターの精度が向上しますが、DEFENDER FOR OFFICE 365の前にESG があり、現在 EOP フィルタリングをバイパスしていない場合、特定のメッセージの配信可能性が変わる可能性があります。 影響は EOP ポリシーに限定されます。評価の一環として設定されたDefender for Office 365 ポリシーは、非適用モードで作成されます。 運用環境への潜在的な影響を最小限に抑えるために、メッセージのスパム信頼レベル (SCL) を -1 に設定するメール フロー ルール (トランスポート ルールとも呼ばれます) を作成することで、ほとんどの EOP フィルター処理をバイパスできます。 詳細については、「[メール フロー ルールを使用して、Exchange Onlineのメッセージでスパム信頼レベル (SCL) を設定](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)する」を参照してください。

評価モードを設定すると、ポリシーが実装された場合にブロックされたメッセージを定量化する最大 90 日間のデータを含む日次レポートが表示されます (削除、迷惑メールへの送信、検疫など)。 レポートは、すべてのDefender for Office 365および EOP 検出に対して生成されます。 レポートは検出テクノロジごとに集計され (偽装など)、時間範囲でフィルター処理できます。 さらに、メッセージ レポートをオンデマンドで作成して、カスタム ピボットを作成したり、エクスプローラーを使用して詳細なメッセージを作成したりできます。

簡単なセットアップ エクスペリエンスを使用すると、次の点に重点を置くことができます。

- 評価の実行
- 詳細なレポートを取得する
- アクションのレポートの分析
- 評価結果を提示する

## <a name="before-you-begin"></a>はじめに

### <a name="licensing"></a>ライセンス

評価にアクセスするには、ライセンス要件を満たす必要があります。 次のいずれかのライセンスが機能します。

- Microsoft Defender for Office 365 プラン 1
- Microsoft Defender for Office 365 プラン 2
- Microsoft 365 E5、Microsoft 365 E5 Security
- Office 365 E5

これらのライセンスのいずれかを持っていない場合は、試用版ライセンスを取得する必要があります。

#### <a name="trial"></a>試用版

Microsoft Defender for Office 365の試用版ライセンスを取得するには、**課金管理者ロール** または **グローバル管理者ロール** が必要です。 グローバル管理者ロールを持つユーザーにアクセス許可を要求します。 [サブスクリプションとライセンスについて学習する](../../commerce/licenses/subscriptions-and-licenses.md)

適切なロールを取得したら、Microsoft 365 管理センターで<https://admin.microsoft.com>Microsoft Defender for Office 365 (プラン 2) の試用版ライセンスを取得し、**課金** \> **購入サービス** に移動して、次に課金サービスを見つけて選択することをお勧めします。Microsoft Defender for Office 365 (プラン 2) 試用版。 または、試用版ページに直接移動するには、 <https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)> 試用版には 25 ライセンスの 30 日間の無料試用版が含まれています。

高度な脅威を監視および報告するための評価を含む 30 日間のウィンドウが表示されます。 完全なDefender for Office 365機能が必要な場合は、有料サブスクリプションを購入することもできます。

### <a name="roles"></a>役割

**評価モードでDefender for Office 365** を設定するには、Exchange Online ロールが必要です。 Microsoft 365 コンプライアンスまたはセキュリティ管理者ロールの割り当ては機能しません。

- [Exchange Onlineのアクセス許可の詳細](/exchange/permissions-exo/permissions-exo)
- [管理者ロールの割り当ての詳細](../../admin/add-users/assign-admin-roles.md)

次のロールが必要です。

|タスク|ロール (Exchange Online)|
|---|---|
|無料試用版を入手するか、Microsoft Defender for Office 365を購入する (プラン 2)|課金管理者ロールまたはグローバル管理者ロール|
|評価ポリシーを作成する|リモートドメインと承認済みドメインロール。セキュリティ管理者ロール|
|評価ポリシーを編集する|リモートドメインと承認済みドメインロール。セキュリティ管理者ロール|
|評価ポリシーを削除する|リモートドメインと承認済みドメインロール。セキュリティ管理者ロール |
|評価レポートを表示する|セキュリティ管理者ロールまたはセキュリティ リーダー ロール|

### <a name="enhanced-filtering-for-connectors"></a>コネクタのフィルター処理の強化

一括保護やスパム保護など、Exchange Online Protection ポリシーは変わりません。 ただし、評価ではコネクタの強化されたフィルター処理が有効になり、バイパスされない限り、メール フローとExchange Online Protection ポリシーに影響を与える可能性があります。

コネクタのフィルター処理の強化により、テナントはスプーフィング対策保護を使用できます。 コネクタの拡張フィルター処理をオンにせずに電子メール セキュリティ ゲートウェイ (ESG) を使用している場合、スプーフィング対策はサポートされません。

### <a name="urls"></a>URL

URL はメール フロー中にデトネーションされます。 特定の URL をデトネーションしたくない場合は、許可されている URL の一覧を適切に管理します。 詳細については、「 [テナント許可/ブロック リストの管理](tenant-allow-block-list.md) 」を参照してください。

メール メッセージ本文の URL リンクは折り返されないため、顧客への影響が軽減されます。

### <a name="email-routing"></a>Email ルーティング

メールをルーティングする受信コネクタの名前など、メールの現在のルーティング方法を設定するために必要な対応する詳細を準備します。 Exchange Online Protectionのみを使用している場合は、コネクタがありません。 [メール フローとメール ルーティングについて学習する](/office365/servicedescriptions/exchange-online-service-description/mail-flow)

サポートされている電子メール ルーティングのシナリオは次のとおりです。

- **サード パーティ のパートナーまたはオンプレミスのサービス プロバイダー**: 評価する受信コネクタは、サードパーティ プロバイダーを使用するか、オンプレミスの電子メール セキュリティのソリューションを使用しています。
- **Microsoft Exchange Online保護のみ**: 評価するテナントは、電子メール セキュリティにOffice 365を使用し、Mail Exchange (MX) レコードは Microsoft を指します。

### <a name="email-security-gateway"></a>Email セキュリティ ゲートウェイ

サード パーティの電子メール セキュリティ ゲートウェイ (ESG) を使用している場合は、プロバイダーの名前を知っている必要があります。 オンプレミスの ESG またはサポートされていないベンダーを使用している場合は、デバイスのパブリック IP アドレスを把握している必要があります。

サポートされているサード パーティパートナーは次のとおりです。

- バラクーダ
- IronPort
- Mimecast
- Proofpoint
- ソフォス
- Symantec
- Trend Micro

### <a name="scoping"></a>スコープ

評価の範囲を受信コネクタに設定できます。 コネクタが構成されていない場合、評価スコープを使用すると、管理者はテナント内の任意のユーザーからデータを収集してDefender for Office 365を評価できます。

## <a name="get-started-with-the-evaluation"></a>評価の概要

Microsoft 365 Defender ポータルで、次のアクセス ポイントからMicrosoft Defender for Office 365評価セットアップ カードを見つけます。

- **エンドポイント** \>**脆弱性の管理** \>**ダッシュボード** (<https://security.microsoft.com/tvm_dashboard>)
- **Email & コラボレーション** \> **ポリシー & ルール** \> **脅威ポリシー** (<https://security.microsoft.com/threatpolicy>)
- **レポート** \>**Email & コラボレーション** \> **Email & コラボレーション レポート** (<https://security.microsoft.com/emailandcollabreport>)

## <a name="setting-up-the-evaluation"></a>評価の設定

評価のセットアップ フローを開始すると、2 つのルーティング オプションが与えられます。 組織のメール ルーティングのセットアップと評価のニーズに応じて、サード パーティまたはオンプレミスのサービス プロバイダーを使用するか、Microsoft Exchange Onlineのみを使用するかを選択できます。

- サード パーティのパートナーやオンプレミスのサービス プロバイダーを使用している場合は、ドロップダウン メニューからベンダーの名前を選択する必要があります。 その他のコネクター関連の詳細を入力します。

- MX レコード **が** Microsoft を指していて、Exchange Online メールボックスがある場合は、Microsoft Exchange Onlineを選択します。

設定を確認し、必要に応じて編集します。 次に、[ **評価の作成**] を選択します。 セットアップが完了したことを示す確認メッセージが表示されます。

Microsoft Defender for Office 365評価レポートは 1 日に 1 回生成されます。 データの入力には最大で 24 時間かかる場合があります。

### <a name="exchange-mail-flow-rules-optional"></a>Exchange メール フロー ルール (省略可能)

既存のゲートウェイがある場合、評価モードを有効にすると、コネクタの拡張フィルター処理がアクティブになります。 この機能により、受信送信者の IP アドレスを変更することで、フィルター処理の精度が向上します。 この機能によってフィルターの判定が変更される可能性があり、Exchange Online Protectionをバイパスしない場合、特定のメッセージの配信可能性が変わる可能性があります。 この場合、影響を分析するためにフィルター処理を一時的にバイパスすることができます。 フィルター処理をバイパスするには、メッセージの SCL を -1 に設定するメール フロー ルール (トランスポート ルールとも呼ばれます) を Exchange 管理センター (EAC) に <https://admin.exchange.microsoft.com/#/transportrules> 作成します (まだない場合)。 手順については、「[メール フロー ルールを使用して、Exchange Online内のメッセージでスパム信頼レベル (SCL) を設定する」を](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)参照してください。

## <a name="evaluate-capabilities"></a>機能を評価する

評価レポートが生成されたら、組織内の電子メールとコラボレーション ワークスペースで、高度な脅威リンク、高度な脅威の添付ファイル、および潜在的な偽装が識別された数を確認します。

試用版の有効期限が切れた後は、90 日間レポートにアクセスし続けることができます。 ただし、それ以上の情報は収集されません。 試用版の有効期限が切れた後もMicrosoft Defender for Office 365を引き続き使用する場合は、[Microsoft Defender for Office 365 (プラン 2) の有料サブスクリプションを必ず購入](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)してください。

**[設定]** に移動して、ルーティングを更新したり、評価をいつでも無効にしたりできます。 ただし、オフにした後も評価を続行することにした場合は、同じセットアップ プロセスをもう一度実行する必要があります。

## <a name="provide-feedback"></a>フィードバックの提供

お客様のフィードバックは、高度な攻撃から環境を保護するのに役立ちます。 製品の機能と評価結果のエクスペリエンスと印象を共有します。

[ **フィードバックの送信** ] を選択して、ご意見をお聞かせください。
