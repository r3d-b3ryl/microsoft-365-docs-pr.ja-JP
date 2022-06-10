---
title: 基本的なモビリティとセキュリティの機能
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: 基本的なモビリティとセキュリティは、組織Microsoft 365電子メールやドキュメントへのアクセスを制御するポリシーを使用してモバイル デバイスをセキュリティで保護および管理するのに役立ちます。
ms.openlocfilehash: 55c2a197959e55e2a74f8691b7181f8ee91b0ea9
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66010170"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>基本的なモビリティとセキュリティの機能

基本的なモビリティとセキュリティは、組織内のライセンスMicrosoft 365ユーザーが使用する iPhone、iPad、Android、Windows Phone などのモバイル デバイスをセキュリティで保護および管理するのに役立ちます。 サポートされているモバイル デバイスとアプリの組織のMicrosoft 365メールやドキュメントへのアクセスを制御するのに役立つ設定を使用して、モバイル デバイス管理ポリシーを作成できます。 デバイスの紛失または盗難時には、リモートからデバイスをワイプして、組織の機密情報を削除できます。

## <a name="supported-operating-systems"></a>サポートされるオペレーティング システム

Basic Mobility and Security によってデバイスでサポートされる最小のオペレーティング システムについては、Microsoft Intune オペレーティング システム ガイドに従ってください。 詳細については、[サポートされているオペレーティング システムIntune](/mem/intune/fundamentals/supported-devices-browsers)参照してください。

Basic Mobility and Security を使用して、次のデバイスをセキュリティで保護および管理できます。

- iOS
- Android (Samsung Knox を含む)<sup>1</sup>
- Windows <sup>2、3</sup>

<sup>1</sup>2020 年 6 月以降、Android バージョン 9 より前のバージョンでは、Samsung Knox デバイスを除き、パスワード設定を管理できません。

<sup>2</sup>Windows 8.1 RT デバイスのアクセス制御は、Exchange ActiveSyncに制限されます。

<sup>3</sup>Windows 10のアクセス制御には、Azure AD Premiumを含むサブスクリプションが必要であり、デバイスをAzure Active Directoryに参加させる必要があります。

> [!NOTE]
> 以前の OS バージョンに既に登録されているデバイスは引き続き機能しますが、機能は予告なしに変更される可能性があります。

組織内のユーザーが Basic Mobility and Security でサポートされていないモバイル デバイスを使用している場合は、組織のデータのセキュリティを強化するために、それらのデバイスのMicrosoft 365電子メールへのExchange ActiveSyncアプリ アクセスをブロックすることができます。 Exchange ActiveSyncをブロックする手順については、「[Basic Mobility and Security でデバイス アクセス設定を管理する」を参照してください](manage-device-access-settings.md)。

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Microsoft 365電子メールとドキュメントのアクセス制御

次の表に示すさまざまな種類のモバイル デバイスでサポートされているアプリは、ユーザーのデバイスに適用される新しいモバイル デバイス管理ポリシーがあり、ユーザーが以前にデバイスを登録していない、Basic Mobility and Security に登録するようユーザーに求めます。 ユーザーのデバイスがポリシーに準拠していない場合、ポリシーの設定方法によっては、ユーザーがこれらのアプリ内のMicrosoft 365リソースへのアクセスをブロックされたり、アクセス権を持っていてもポリシー違反が報告Microsoft 365場合があります。

|製品|iOS|Android|
|---|---|---|
|**Exchange** Exchange ActiveSyncには、Exchange ActiveSyncバージョン 14.1 以降を使用する組み込みの電子メール アプリと TouchDown などのサードパーティ製アプリが含まれています。|メール|メール|
|**Office** および **OneDrive for Business**|Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**スマートフォンとタブレットの場合**:<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **電話のみ:** <br/> Office Mobile|

> [!NOTE]
>
> - iOS 10.0 以降のバージョンのサポートには、iPhone デバイスとiPad デバイスが含まれます。
> - BlackBerry OS デバイスの管理は、Basic Security and Mobility ではサポートされていません。 BlackBerry の BlackBerry Business Cloud Services (BBCS) を使用して、BlackBerry OS デバイスを管理します。 Android OS を実行している Blackberry デバイスは、標準のAndroid デバイスとしてサポートされています
> - モバイル ブラウザーを使用してMicrosoft 365 SharePoint サイト、Office Online のドキュメント、またはOutlook Web Appの電子メールにアクセスする場合、ユーザーは登録を求められず、ポリシー違反でブロックまたは報告されることはありません。

次の図は、新しいデバイスを持つユーザーが、Basic Mobility and Security によるアクセス制御をサポートするアプリにサインインした場合の動作を示しています。 ユーザーは、デバイスを登録するまでアプリ内のMicrosoft 365リソースへのアクセスをブロックされます。

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本的なモビリティとセキュリティのアクセス制御。":::

> [!NOTE]
> Microsoft 365 Business Standardの基本的なモビリティとセキュリティで作成されたポリシーとアクセス規則は、Exchange管理センターで作成Exchange ActiveSyncモバイル デバイス メールボックス ポリシーとデバイス アクセス規則をオーバーライドします。 デバイスが basic Mobility and Security for Microsoft 365 Business Standard に登録されると、デバイスに適用されたモバイル デバイス メールボックス ポリシーまたはデバイス アクセス規則Exchange ActiveSyncは無視されます。 Exchange ActiveSyncの詳細については、Exchange Online[のExchange ActiveSyncを](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)参照してください。

## <a name="policy-settings-for-mobile-devices"></a>モバイル デバイス用のポリシー設定

特定の設定をオンにしてアクセスをブロックするポリシーを作成した場合、メールやドキュメントのアクセス制御に一覧表示されているサポートされているアプリを使用すると、ユーザーは[Microsoft 365リソースへのアクセスをブロックMicrosoft 365](capabilities.md)。

ユーザーがMicrosoft 365リソースにアクセスできないようにする設定は、次のセクションにあります。

- セキュリティ

- 暗号化

- 脱獄

- 管理された電子メール プロファイル

例として次の図は、登録済みデバイスを使用しているユーザーが、そのデバイスに適用されるモバイル デバイス管理ポリシーのセキュリティ設定を満たしていない場合の動作を示しています。 ユーザーは、Basic Mobility and Security によるアクセス制御をサポートするアプリにサインインします。 デバイスがセキュリティ設定に準拠するまで、アプリ内のMicrosoft 365リソースへのアクセスはブロックされます。

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="基本的なモビリティとセキュリティのコンプライアンス メッセージ。":::

次のセクションでは、Microsoft 365組織のリソースに接続するモバイル デバイスをセキュリティで保護して管理するために使用できるポリシー設定の一覧を示します。

## <a name="security-settings"></a>セキュリティの設定

|設定名|iOS|Android|Samsung Knox|
|---|---|---|---|
|パスワードを要求|はい|はい|はい|
|シンプルなパスワードを禁止|はい|不要|不要|
|英数字のパスワードを要求|はい|不要|不要|
|パスワードの最小文字数|はい|はい|はい|
|デバイスがワイプされるまでのサインイン失敗回数|はい|はい|はい|
|デバイスがロックされるまでのアイドル時間 (分)|はい|はい|はい|
|パスワードの有効期限 (日)|はい|はい|はい|
|パスワードの履歴を記憶して再利用を防止|はい|はい|はい|

## <a name="encryption-settings"></a>暗号化の設定

|設定名|iOS|Android|Samsung Knox|
|---|---|---|---|
|デバイス<sup>1</sup> でデータ暗号化を要求する|不要|はい|はい|

<sup>1</sup>Samsung Knox では、ストレージ カードで暗号化を要求することもできます。

## <a name="jail-broken-setting"></a>脱獄の設定

|設定名|iOS|Android|Samsung Knox|
|---|---|---|---|
|デバイスの脱獄またはルート化はできません|はい|はい|はい|

## <a name="managed-email-profile-option"></a>管理された電子メール プロファイルのオプション

次のオプションを使用すると、ユーザーが手動で作成した電子メール プロファイルを使用している場合に、ユーザーが自分のMicrosoft 365メールにアクセスできないようにすることができます。 iOS デバイスを使用しているユーザーは、電子メールにアクセスする前に、手動で作成した電子メール プロファイルを削除しておく必要があります。 プロファイルを削除すると、デバイスに新しいプロファイルが自動的に作成されます。 エンド ユーザーが準拠する方法については、「 [既存のメール アカウントが見つかりました](/intune-user-help/existing-company-email-account-found)」を参照してください。

|設定名|iOS|Android|Samsung Knox|
|---|---|---|---|
|電子メール プロファイルが管理されている|はい|不要|不要|

## <a name="cloud-settings"></a>クラウドの設定

|設定名|iOS|Android|Samsung Knox|
|---|---|---|---|
|暗号化されたバックアップを要求|はい|不要|不要|
|クラウド バックアップの禁止|はい|不要|不要|
|ドキュメントの同期の禁止|はい|不要|不要|
|写真の同期の禁止|はい|不要|不要|
|Google のバックアップを許可する|該当なし|いいえ|はい|
|Google アカウントの自動同期を許可する|該当なし|いいえ|はい|

## <a name="system-settings"></a>システムの設定

|設定名|iOS|Android|Samsung Knox|
|---|---|---|---|
|画面キャプチャの禁止|はい|不要|はい|
|デバイスからの診断データ送信の禁止|はい|不要|はい|

## <a name="application-settings"></a>アプリケーションの設定

|設定名|iOS|Android|Samsung Knox|
|---|---|---|---|
|デバイスでのビデオ会議をブロックする|はい|不要|不要|
|アプリケーション ストアへのアクセスをブロックする|はい|不要|はい|
|アプリケーション ストアへアクセスする際にパスワードを要求する|不要|はい|はい|

## <a name="device-capabilities-settings"></a>デバイスの機能の設定

|設定名|iOS|Android|Samsung Knox|
|---|---|---|---|
|リムーバブル記憶域との接続の禁止|はい|はい|不要|
|Bluetooth 接続の禁止|はい|はい|不要|

## <a name="additional-settings"></a>その他の設定

Security & Compliance PowerShell コマンドレットを使用して、次の追加のポリシー設定を設定できます。 詳細については、「[セキュリティ/コンプライアンス PowerShell](/powershell/exchange/scc-powershell)」を参照してください。

|設定名|iOS|Android|
|---|---|---|
|CameraEnabled|はい|はい|
|RegionRatings|はい|不要|
|MoviesRatings|はい|不要|
|TVShowsRating|はい|不要|
|AppsRatings|はい|不要|
|AllowVoiceDialing|はい|不要|
|AllowVoiceAssistant|はい|不要|
|AllowAssistantWhileLocked|はい|不要|
|AllowPassbookWhileLocked|はい|不要|
|MaxPasswordGracePeriod|はい|不要|
|PasswordQuality|いいえ|はい|
|SystemSecurityTLS|はい|不要|
|WLANEnabled|いいえ|いいえ|

## <a name="settings-supported-by-windows"></a>Windowsでサポートされている設定

Windows 10デバイスは、モバイル デバイスとして登録することで管理できます。 該当するポリシーをデプロイした後、Windows 10 デバイスを持つユーザーは、組み込みの電子メール アプリを初めて使用してMicrosoft 365メールにアクセスする (Azure AD Premium サブスクリプションが必要) 場合、Basic Mobility and Security に登録する必要があります。

モバイル デバイスとして登録されているWindows 10 デバイスでは、次の設定がサポートされます。 これらの設定では、ユーザーがMicrosoft 365リソースにアクセスすることをブロックすることはありません。

### <a name="security-settings"></a>セキュリティの設定

- 英数字のパスワードを要求

- パスワードの最小文字数

- デバイスがワイプされるまでのサインイン失敗回数

- デバイスがロックされるまでのアイドル時間 (分)

- パスワードの有効期限 (日)

- パスワードの履歴を記憶して再利用を防止

> [!NOTE]
> パスワードを制御する次の設定は、ローカル Windows アカウントのみを制御します。 ドメインへの参加またはAzure Active Directoryを通じて提供されるWindowsアカウントは、これらの設定の影響を受けられません。

### <a name="system-settings"></a>システムの設定

デバイスからの診断データの送信をブロックします。

### <a name="additional-settings"></a>その他の設定

PowerShell コマンドレットを使用して、次の追加のポリシー設定を設定できます。

- AllowConvenienceLogon

- UserAccountControlStatus

- FirewallStatus

- AutoUpdateStatus

- AntiVirusStatus

- AntiVirusSignatureStatus

- SmartScreenEnabled

- WorkFoldersSyncUrl

## <a name="remotely-wipe-a-mobile-device"></a>モバイル デバイスをリモートからワイプする

デバイスが紛失または盗難にあった場合は、機密組織のデータを削除し、**Microsoft Purview コンプライアンス ポータル** > の **データ損失防止** > **デバイス管理** からワイプを実行することで、Microsoft 365組織のリソースへのアクセスを防ぐことができます。 個別のワイプで組織のデータのみを削除することも、全体のワイプでデバイスからすべての情報を削除して出荷時の設定に戻すこともできます。

詳細については、「 [基本的なモビリティとセキュリティでモバイル デバイスをワイプする」を参照してください](wipe-mobile-device.md)。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365の基本的なモビリティとセキュリティの概要](overview.md) (記事)\
[Basic Mobility and Security でデバイス セキュリティ ポリシーを作成する](create-device-security-policies.md) (記事)
