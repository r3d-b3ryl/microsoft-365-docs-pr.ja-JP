---
title: Microsoft Defender for Office 365 の評価
description: 評価モードでの Office 365 の defender では、verdicts (マルウェアなど) をログに記録し、メッセージに対しては処理しない Office 365 の電子メールポリシーを作成します。
keywords: office 365、Microsoft Defender for Office 365、office 365 評価、試用版 office 365、Microsoft Defender、ATP を評価する
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
ms.openlocfilehash: b5b095a1d75ead0f963a71d816e7d879b7cd3697
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614800"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の評価

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Microsoft Defender for Office 365 の評価は、すぐにパブリックプレビューに表示されます。 このプレビュー版は、サービスレベル契約なしで提供されます。 一部の機能はサポートされていない場合や、制限された機能を備えている場合があります。

包括的なセキュリティ製品の評価を実施することで、アップグレードと購入に関する情報を得られるようになります。 セキュリティ製品の機能を試して、毎日のタスクでセキュリティ運用チームをどのように支援するかを評価することができます。

[Microsoft Defender For Office 365](office-365-atp.md)の評価の体験は、セキュリティソリューションの機能を評価することに重点を置くために、デバイスと環境の構成の複雑さを排除するように設計されています。 これは、SharePoint、Office クライアント、または Teams ではなく、電子メール保護にのみ適用されます。

Office 365 用の Microsoft Defender をサポートするライセンスをまだ持っていない場合は、 [無料の30日間の評価](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) を開始して、Office 365 セキュリティ & コンプライアンスセンターで機能をテストでき https://protection.office.com/homepage) ます (。 クイックセットアップを楽しんで、必要に応じて簡単にオフにすることができます。

## <a name="how-the-evaluation-works"></a>評価のしくみ

評価モードでの Office 365 の defender では、verdicts (マルウェアなど) をログに記録し、メッセージに対しては処理しない Office 365 の電子メールポリシーを作成します。 MX レコード構成を変更する必要はありません。

評価モード、 [安全な添付ファイル](atp-safe-attachments.md)、 [安全なリンク](atp-safe-links.md)、および [フィッシング対策ポリシー](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) は、お客様の代わりにセットアップされます。 すべての Defender for Office 365 ポリシーは、バックグラウンドで非強制モードで作成され、ユーザーには表示されません。

セットアップの一環として、評価モードでは、 [コネクタの拡張フィルター処理](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)も構成されます。 IP アドレスと送信者情報を保持することで、フィルターの精度が向上します。これは、メールが Office 365 の Defender の前にある電子メールセキュリティゲートウェイ (ESG) を通過するときには失われます。 これにより、Exchange Online Protection (EOP) スパム対策ポリシーとフィッシング対策ポリシーのフィルターの精度も向上します。

サポートされていないシナリオによって生産上の影響を最小限に抑えるには、スパム信頼レベル (SCL) を-1 に設定するトランスポートルールを作成して、すべての EOP フィルタリングをバイパスします。 詳細については [、「EAC を使用してメッセージの SCL を設定するメールフロールールを作成する」を](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)参照してください   。

評価モードが設定されている場合、毎日最大90日間のデータ量を含むレポートが更新されます。ブロックされたメッセージは、削除、迷惑メールへの送信などのポリシーが作成および実装されていました。 すべての Defender for Office 365 と EOP の検出に関するレポートが生成されます。 これらは検出テクノロジ (たとえば、偽装) ごとに集計され、時間範囲によってフィルター処理できます。 さらに、メッセージレポートをオンデマンドで作成して、カスタムピボットを作成したり、脅威エクスプローラーを使用して詳細なメッセージを表示したりできます。

シンプルなセットアップ環境を使用すると、以下のことに集中できます。

- 評価を実行する
- 詳細レポートを取得する
- アクションのレポートを分析する
- 評価結果の提示

## <a name="before-you-begin"></a>開始する前に

### <a name="licensing"></a>ライセンス

評価にアクセスするには、ライセンス要件を満たす必要があります。 次のいずれかのライセンスが機能します。

- Microsoft Defender for Office 365 プラン1
- Microsoft Defender for Office 365 プラン2
- Microsoft 365 E5、Microsoft 365 E5 セキュリティ
- Office 365 E5

これらのライセンスのいずれかがない場合は、試用版ライセンスを取得する必要があります。

#### <a name="trial"></a>試用版

Microsoft Defender for Office 365 の試用版ライセンスを取得するには、 **課金管理者** ロールまたは **グローバル管理者ロール** を持っている必要があります。 グローバル管理者の役割を持つユーザーからアクセス許可を要求します。 [サブスクリプションとライセンスについて](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

適切な役割を持っている場合は、365 Microsoft Defender for Office 365 (Plan 2) の試用版ライセンスを取得するには、「Billing > Purchase services」にアクセスすることをお勧めします。 試用版には、30日間の無料試用版の25ライセンスが含まれています。 [Microsoft Defender For Office 365 (Plan 2) の試用版を取得](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)します。

高度な脅威を監視して報告するための評価については、30日間のウィンドウが用意されています。 Office 365 の機能を完全に Defender 使用する場合は、有料サブスクリプションを購入するオプションもあります。

### <a name="roles"></a>ロール

評価モードで Office 365 の Defender をセットアップするには、Exchange Online の役割が必要です。 次の役割が必要です。

|タスク|Role|
|---|---|
|無料試用版を入手するか、Microsoft Defender for Office 365 (Plan 2) を購入する|課金管理者の役割またはグローバル管理者の役割|
|評価ポリシーを作成する|[リモートドメインと承認済みドメイン] 役割セキュリティ管理者の役割|
|評価ポリシーの編集|[リモートドメインと承認済みドメイン] 役割セキュリティ管理者の役割|
|評価ポリシーを削除する|[リモートドメインと承認済みドメイン] 役割セキュリティ管理者の役割 |
|評価レポートを表示する|セキュリティ管理者の役割またはセキュリティリーダーの役割|
|

### <a name="enhanced-filtering"></a>拡張されたフィルター処理

一括保護やスパム対策など、Exchange Online の保護ポリシーは変わりません。 メッセージ配信も同じままです。 ただし、この評価は、メールフローと Exchange Online Protection ポリシーに影響するコネクタの拡張されたフィルター処理を有効にします。

コネクタのフィルター処理を強化することで、テナントがスプーフィング対策保護を使用できるようになります。 メールセキュリティゲートウェイ (ESG) を使用していても、コネクタの拡張フィルター処理を有効にしていない場合、スプーフィング対策はサポートされません。

### <a name="urls"></a>URL

メールフローでは、Url は分析になります。 特定の Url を分析したくない場合は、許可された Url のリストを適切に管理します。 詳細について [は、「テナントの許可/ブロック」リストの「Manage URLs](tenant-allow-block-list.md) 」を参照してください。

電子メールメッセージの本文内の URL リンクは、顧客への影響を軽減するために折り返されません。

### <a name="email-routing"></a>電子メールルーティング

メールをルーティングする受信コネクタの名前など、電子メールの現在のルーティング方法を設定するために必要な対応する詳細を準備する必要があります。 Exchange Online Protection のみを使用している場合は、コネクタがありません。 [メールフローと電子メールルーティングについて](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)

サポートされている電子メールルーティングのシナリオは次のとおりです。

- **サードパーティのパートナーまたはオンプレミスのサービスプロバイダー**: 評価する受信コネクタがサードパーティプロバイダーを使用しているか、オンプレミスのメールセキュリティ用のソリューションを使用しています。
- **Microsoft Exchange Online Protection のみ**: 評価するテナントは、電子メールのセキュリティに Office 365 を使用し、メール交換 (MX) レコードは Microsoft を指しています。

### <a name="email-security-gateway"></a>電子メールセキュリティゲートウェイ

サードパーティの電子メールセキュリティゲートウェイ (ESG) を使用している場合は、プロバイダーの名前を知る必要があります。 ESG オンプレミスまたはサポートされていないベンダーを使用している場合は、デバイスのパブリック IP アドレスを知っている必要があります。

サポートされているサードパーティパートナーは次のとおりです。

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- Sophos
- 社
- トレンドマイクロ

### <a name="scoping"></a>スコープ

評価を受信コネクタに適用することができます。 コネクタが構成されていない場合は、評価スコープによって、管理者がテナント内の任意のユーザーからデータを収集し、Office 365 の Defender を評価することができます。

## <a name="get-started-with-the-evaluation"></a>評価を開始する

Office 365 Security & コンプライアンスセンター (3 つのアクセスポイント) で、Microsoft Defender for Office 365 評価版カードを検索し https://protection.office.com/homepage) ます。

- 脅威管理 > ダッシュボード
- 脅威管理 > ポリシー
- レポート > ダッシュボード

## <a name="setting-up-the-evaluation"></a>評価の設定

評価のためにセットアップフローを開始すると、2つのルーティングオプションが表示されます。 組織のメールルーティングのセットアップと評価のニーズに応じて、サードパーティのサービスプロバイダーとオンプレミスまたはその両方、または Microsoft Exchange Online のみを使用しているかどうかを選択できます。

- サードパーティのパートナーやオンプレミスのサービスプロバイダーを使用している場合は、ドロップダウンメニューからベンダー名を選択する必要があります。 その他のコネクタ関連の詳細を提供します。

- MX レコードが Microsoft を指していて、Exchange Online メールボックスを持っている場合は、Microsoft Exchange Online を選択します。

設定を確認し、必要に応じて編集します。 [評価の **作成**] を選択します。 セットアップが完了したことを示す確認メッセージが表示されます。

Microsoft Defender for Office 365 評価レポートは、1日に1回生成されます。 データの入力には最大24時間かかる場合があります。

### <a name="exchange-rules-optional"></a>Exchange ルール (オプション)

既存のゲートウェイを使用している場合は、コネクタの拡張フィルター処理を有効にし、受信側の送信元 IP アドレスを変更するため、フィルター処理をバイパスすることをお勧めします。 バイパスするには、Exchange 管理センターに移動し、SCL-1 のポリシーを作成します (まだ使用していない場合)。 ルールコンポーネントの詳細と動作方法については、「Exchange Online のメールフロールール (トランスポートルール)」を参照してください。

## <a name="evaluate-capabilities"></a>機能を評価する

評価レポートが生成された後、組織内の電子メールおよびコラボレーションワークスペースで、高度な脅威のリンク数、高度な脅威の添付ファイル、および潜在的な impersonations が特定されているかどうかを確認します。

試用期間が終了したら、90日間レポートへのアクセスを続行できます。 ただし、これ以上情報は収集されません。 試用期間が終了した後に Microsoft Defender for Office 365 を引き続き使用する場合は、 [Microsoft defender For office 365 (Plan 2) の有料サブスクリプションを購入](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)してください。

[ **設定** ] に移動すると、ルーティングを更新したり、いつでも評価をオフにしたりできます。 ただし、同じセットアッププロセスをもう一度実行する必要があります。これをオフにした後に評価を続行することを決定します。

## <a name="provide-feedback"></a>フィードバックの提供

フィードバックは、高度な攻撃から環境を保護する上で役に立ちます。 製品の機能や評価結果の印象とインプレッションを共有します。

[ **フィードバックを提供** する] を選択して、ご意見をお聞かせください。
