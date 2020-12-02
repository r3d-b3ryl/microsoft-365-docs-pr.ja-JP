---
title: Microsoft クラウドの移行のためのその他の作業前の情報
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '概要: 新しいドイツデータセンターリージョンで、Microsoft Cloud ドイツ (Microsoft Cloud Deut上陸ランド) から Office 365 サービスに移行する際の追加の準備作業について説明します。'
ms.openlocfilehash: 41953aa9d91faa91bd983fbbc8d93baf08c172ed
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551711"
---
# <a name="additional-pre-work-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft クラウドの移行のためのその他の作業前の情報

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| [Office 365 サービスの url と IP アドレス](https://aka.ms/o365urls)へのネットワーク接続を確保します。 | Office 365 サービスへのアクセスに使用されるお客様がホストするすべてのクライアントおよびサービスは、Office 365 サービスエンドポイントにアクセスできる必要があります。 | すべての移行先のお客様、およびネットワークアクセスを使用しているお客様は、Microsoft Cloud Deut上陸ランドに限定されます。 | 必須のアクションです。 Inaction は、サービスまたはクライアントソフトウェアでエラーが発生する可能性があります。 |
| 移行に関連する DNS の変更を確認して準備します。 | お客様は、Exchange Online と Exchange Online Protection (MX レコードなど) の DNS エントリを準備します。 | Exchange Online のお客様 | この操作は推奨されています。 何もしない場合、移行したお客様のメールは、Microsoft cloud deut上陸陸上サービスが無効になるまで、Microsoft Cloud Deut上陸を経由してルーティングされる可能性があります。 |
| 移行に関連する DNS の変更を確認して準備します。 | Skype for Business Online のお客様が所有している DNS ゾーンの変更。 | Skype For Business Online のお客様 | -DNS レコードの更新を早めるには、ユーザーが所有するドメイン DNS レコードの Time-to-live (TTL) を5分に更新することをお勧めします。 ただし、この DNS 変更に関連付けられている Microsoft 管理のカットオーバーは、24時間の変更ウィンドウ内でいつでも発生する可能性があります。 <br><br> -今後、サービスの中断が発生する可能性があります。 ユーザーは、Skype for Business にログインすることはできません。 Office 365 サービスで移行した Teams にリダイレクトされます。 |
| Microsoft Teams への移行のためのエンドユーザーおよび管理者トレーニングと準備状況を準備します。 | ユーザーのコミュニケーションと準備状況を計画することで、Skype から Teams への移行を成功させることができます。 | Skype For Business Online のお客様 | -クライアントは新しいサービスを認識する必要があります。また、サービスが Office 365 サービスに移行された場合の使用方法についても理解しておく必要があります。 <br><br> -お客様のバニティドメインと初期ドメインの両方に対して DNS の変更が行われた後、ユーザーは Skype for Business にサインインして、それが Teams に移行されることを確認できます。 これにより、Teams のデスクトップクライアントもバックグラウンドでダウンロードされます。 |
| Microsoft Outlook for iOS および Android 用のアカウントを削除して再追加するユーザーに関するエンドユーザーおよび管理者トレーニングを準備します。 | 新しい Office 365 services の構成を正しく同期するには、Microsoft クラウドのメールボックスで構成されている iOS および Android 用の microsoft Outlook アカウントを削除して、再度 Outlook に追加する必要があります。 | IOS および Android のお客様向け Microsoft Outlook | 以前に Microsoft Cloud Deut上陸を構成した Outlook メールボックスでは、新しい Office 365 サービス構成が取得されず、エラーが発生したり、他のユーザーエクスペリエンスのパフォーマンスが低下したりする可能性があります。 IT 管理者は、移行後にサインインまたはメールの同期に関する問題が発生した場合に、ユーザーが iOS および Android 用の Microsoft Outlook のアカウントを削除して再追加するように事前に指示するドキュメントを提供することをお勧めします。 |
| 移行後に、ユーザーに対してクライアントに対して再起動およびサインインを通知するための準備をします。 | Office クライアントライセンスは、移行中に Microsoft Cloud Deut上陸陸から Office 365 services に移行します。 クライアントは、Office クライアントにサインインアウトした後、新しい有効なライセンスを選択します。 | Microsoft 365 アプリのお客様 |  ユーザーの Office 製品では、Office 365 サービスからライセンスを更新する必要があります。 ライセンスが更新されない場合、Office 製品でライセンス検証エラーが発生することがあります。 |
| 試用版サブスクリプションをすべて取り消します。 | 試用版サブスクリプションは移行されず、有料サブスクリプションの転送がブロックされます。 | すべてのお客様 | 取り消し後にユーザーがアクセスすると、試用サービスは期限切れになり、機能しなくなります。 |
| ドイツで Skype for Business にアクセスするユーザーのために Teams デスクトップクライアントを展開します。 | 移行により、ユーザーはコラボレーション、通話、チャットを行うために Teams に移行されます。 または、Teams デスクトップクライアントを展開するか、サポートされているブラウザーが利用可能であることを確認してください。 | Skype for Business のお客様 | Inaction を実行すると、Teams コラボレーションサービスが利用できなくなります。 |
| Microsoft Cloud Deut上陸陸と Office 365 Services のライセンス機能の違いを分析します。 | Office 365 サービスには、現在の Microsoft Cloud Deut上陸土地では利用できない追加機能とサービスが含まれています。 サブスクリプションの転送時に、ユーザーは新機能を利用できるようになります。 | すべてのお客様 | -Microsoft Cloud Deut上陸陸上および Office 365 サービスのライセンスによって提供されるさまざまな機能を分析します。 [Office 365 プラットフォームサービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)から始めます。 <br><br> -ユーザーまたはユーザー変更管理に対する影響を制限し、必要に応じてユーザーライセンスの割り当てを変更するには、Office 365 サービスの新機能を初期化して無効にする必要があるかどうかを確認します。 <br><br> -Office 365 サービスによって提供される新しいサービスおよび機能については、「ユーザーとヘルプデスクスタッフ」を準備します。 |
| 組織全体の [アイテム保持ポリシー](https://docs.microsoft.com/microsoft-365/compliance/retention) を作成して、移行時に不注意によるコンテンツの削除から保護します。  | -移行中にエンドユーザーがコンテンツを誤って削除しないようにするために、お客様は組織全体のアイテム保持ポリシーを有効にすることを選択できます。 <br><br> -保持は必要ありませんが、移行時に保持される期間は予想どおりに機能するため、保持ポリシーを使用すると、バックアップの安全性メカニズムになります。 同時に、保持ポリシーがすべてのお客様に使用されるわけではありません。特に、保存について懸念している場合があります。 | Office のお客様 | 「アイテム保持ポリシー [と保持ラベルについ](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)て」を参照して、アイテム保持ポリシーを適用します。 |
| 障害復旧シナリオのための[Active Directory フェデレーションサービス (AD FS) ファームのバックアップ](ms-cloud-germany-transition-add-adfs.md#backup)。 | お客様は、証明書利用者がグローバル & ドイツのエンドポイントに信頼できるように、AD FS ファームを適切にバックアップする必要があります。ドメインの発行者 URI に触れることなく復元できます。 Microsoft では、必要に応じて、ファームのバックアップとそれぞれの復元に AD FS ラピッド Restore を使用することをお勧めします。 | フェデレーション認証組織 | 必須のアクションです。 Inaction を実行すると、顧客の AD FS ファームで障害が発生した場合に、移行中にサービスが影響を受ける可能性があります。 |


## <a name="exchange-online"></a>Exchange Online

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Office 365 サービスへの今後の移行について、外部パートナーに通知します。 | 可用性アドレススペース構成を使用すると、Office 365 で空き時間情報を共有できます。 | 予定表と空き時間情報の共有を有効にしている Exchange Online のお客様。 | 必須のアクションです。  これに失敗すると、顧客の移行の後の段階でサービスまたはクライアント障害が発生する可能性があります。 |
|||||

ハイブリッド Exchange を使用している場合:

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 以前のバージョンのハイブリッド構成ウィザード (HCW) をアンインストールし、最新バージョンの17.0.5378.0 をからインストールして実行し [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) ます。 | 最新バージョンの HCW には、Microsoft Cloud Deutare 陸から Office 365 Services に移行しているお客様をサポートするために必要な更新プログラムが含まれています。 <br><br> 更新には、送信コネクタと受信コネクタの社内証明書設定の変更が含まれます。 | ハイブリッド展開を実行している Exchange Online のお客様 | 必須のアクションです。 失敗した場合は、サービスまたはクライアントの障害が発生する可能性があります。 |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint 2013 を使用している場合:

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Sharepoint 2013 ワークフローを制限する。 SharePoint Online の移行時に使用します。 | SharePoint 2013 ワークフローを減らし、移行前に完全なインフライトワークフローを完了します。 | SharePoint Online のお客様 | Inaction は、ユーザーの混乱を招き、ヘルプデスクの呼び出しにつながる可能性があります。 |
|||||

<!--
[Reference:  If Pre-Work][ SharePoint 2013 ]
--> 

## <a name="mobile"></a>Mobile

サードパーティ製のモバイルデバイス管理 (MDM) ソリューションを使用している場合:

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 移行後に再構成が必要かどうかを判断します。 | MDM ソリューションはエンドポイントを対象とする場合があり `outlook.de` ます。 この Office 365 サービスへの移行では、クライアントプロファイルを Office 365 サービス URL に更新する必要があり `outlook.office365.com` ます。 | Exchange Online および MDM のお客様 | エンドポイントにアクセスできる間、クライアントは機能し続けることができ `outlook.de` ますが、Microsoft Cloud Deut上陸陸地のエンドポイントが使用できなくなると失敗します。 |
|||||

<!--
[Reference:  If Pre-Work][ Mobile]
-->             

## <a name="line-of-business-apps"></a>基幹業務アプリ

Office 365 と統合されているサードパーティ製のサービスまたは基幹業務 (LOB) アプリを使用している場合: 

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 移行後に再構成が必要かどうかを判断します。 | サードパーティ製のサービスおよび Office 365 と統合されたアプリケーションは、Microsoft Cloud Deut上陸陸の IP アドレスと Url を想定するようにコーディングされる場合があります。 | すべてのお客様 | 必須のアクションです。 Inaction は、サービスまたはクライアントソフトウェアでエラーが発生する可能性があります。 |
|||||

<!--
[Reference:  If Pre-Work][ LOB]
--> 

## <a name="azure"></a>Azure 

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| パートナーと連携することにより、使用されている Azure サービスを特定し、ドイツから Office 365 services テナントへの今後の移行の準備を行います。 「 [Azure 移行プレイブック](https://docs.microsoft.com/azure/germany/germany-migration-main)」に記載されている手順に従います。 | Azure リソースの移行はお客様の責任にあり、規定の手順を実行する際には手動で作業する必要があります。 Azure サービスの移行を成功させるには、組織で使用されているサービスについて理解することが重要です。 <br><br> Office 365 ドイツのお客様が、同じ id パーティション (組織) を使用して Azure サブスクリプションを所有している場合は、サブスクリプションとサービスの移行を開始する際に、Microsoft が指示する順序に従う必要があります。 | Azure のお客様 | -お客様は、インフラストラクチャ、サービス、およびプラットフォームコンポーネントを含む複数の Azure サブスクリプションを保有している場合があります。 <br><br> -管理者は、この移行イベントの一部として、プロンプトの移行と検証が可能になるように、サブスクリプションと関係者を識別する必要があります。 <br><br> 指定されたタイムライン内のサブスクリプションと Azure コンポーネントの移行が正常に完了しなかった場合、Office および Azure AD の Office 365 サービスへの移行の完了に影響し、データが失われる可能性があります。  <br><br> -メッセージセンターの通知は、顧客主導の移行が開始されるポイントに通知します。 |
|||||

<!--
[Reference:  If Azure Pre-Work][ Azure]
-->  

## <a name="dynamics-365"></a>Dynamics 365

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Dynamics 365 サンドボックスサブスクリプションの場合は、dynamics SQL インスタンスの運用環境を、「Microsoft Cloud Deut上陸陸の Dynamics 365 サブスクリプションからダウンロードしてください。 最新の運用バックアップは、サンドボックスの移行前にサンドボックスに復元する必要があります。 | Dynamics 365 の移行では、ユーザーが最新の運用データベースでサンドボックス環境を確実に更新する必要があります。 | Microsoft Dynamics のお客様 | FastTrack チームは、お客様が乾いた実行を実行して、8. x から 9.1 .x へのバージョンアップグレードを検証することを支援します。 |
|||||

<!--
[Reference: Prework][Dynamics]
-->             

## <a name="power-bi"></a>Power BI

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Power BI Microsoft Cloud Deutランドから Office 365 services に移行されない、Power BI サブスクリプションからのオブジェクトの削除。 | Power BI サービスの移行では、ユーザーがデータセットやダッシュボードなどの特定の成果物を削除する必要があります。 | Power BI のお客様 | 管理者は、次のアイテムをサブスクリプションから削除する必要がある場合があります。 <br> -Real-Time データセット (ストリーミングデータセット、プッシュデータセットなど) <br> -Power BI オンプレミスのデータゲートウェイの構成とデータソース |
|||||

<!--
[Reference: Prework][Power BI]
--> 

## <a name="dns"></a>DNS

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 現在の DNS に MSOID CName エントリがある場合は、DNS 変更を確認して準備します。 | 顧客が所有する DNS ゾーンの変更 | Office クライアントサービスのお客様 | MSOID CName が存在する場合は、顧客が所有する DNS レコードの Time to Live (TTL) を5分に更新します。 |
|||||

<!--
[Reference: Prework][DNS]
-->             

## <a name="federated-identity"></a>フェデレーション ID

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| グローバル Azure AD エンドポイントの証明書利用者信頼を生成します。 | 顧客は、 [グローバル](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) エンドポイントに対して証明書利用者信頼 (RPT) を手動で作成する必要があります。 これを行うには、新しい RPT を GUI で追加します。そのためには、グローバルフェデレーションメタデータ URL を活用し、 [AZURE AD RPT 要求規則](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) を (Ad FS ヘルプで) 使用して、要求規則を生成して RPT にインポートします。 | フェデレーション認証組織 | 必須のアクションです。 Inaction を実行すると、移行中にサービスが影響を受ける可能性があります。 |
|||||

<!--
[Reference: Prework][Federation]
-->  

## <a name="more-information"></a>詳細情報

はじめに:

- [新しいドイツ語のデータセンターリージョンの Microsoft Cloud Deutランドから Office 365 サービスへの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中の顧客の利便性](ms-cloud-germany-transition-experience.md)

遷移を移動します。

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [その他の準備作業](ms-cloud-germany-transition-add-pre-work.md)
- [サービス](ms-cloud-germany-transition-add-general.md)、[デバイス](ms-cloud-germany-transition-add-devices.md)、[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、 [AD FS](ms-cloud-germany-transition-add-adfs.md)の追加情報。

クラウドアプリ:

- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
