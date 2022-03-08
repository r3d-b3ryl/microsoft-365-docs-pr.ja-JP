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
description: 基本的なモビリティとセキュリティは、モバイル デバイスのセキュリティ保護と管理に役立ちます。
ms.openlocfilehash: 04ee7e7dfbc4937d4add2e4c27e7f686b596fadb
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63314883"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>基本的なモビリティとセキュリティの機能

基本的なモビリティとセキュリティは、組織内のライセンスを持つ Microsoft 365 ユーザーが使用する iPhone、iPad、Android、Windows 電話など、モバイル デバイスのセキュリティ保護と管理に役立ちます。 モバイル デバイス管理ポリシーを作成して、サポートされているモバイル デバイスとアプリの組織の電子メールやドキュメントMicrosoft 365を制御するための設定を使用できます。 デバイスの紛失または盗難時には、リモートからデバイスをワイプして、組織の機密情報を削除できます。

## <a name="supported-operating-systems"></a>サポートされるオペレーティング システム

Basic Mobility and Security Microsoft Intuneサポートされている最小オペレーティング システムについては、「オペレーティング システムガイド」の手順に従います。 詳細については、「Intune でサポート [されているオペレーティング システム」を参照してください](/mem/intune/fundamentals/supported-devices-browsers)。

Basic Mobility and Security を使用すると、次のデバイスをセキュリティで保護および管理できます。

- iOS
- Android (Samsung Knox を含む) <sup>1</sup>
- Windows <sup>2、3</sup>

<sup>1</sup>2020 年 6 月以降、9 より後の Android バージョンでは、Samsung Knox デバイス以外のパスワード設定を管理できません。

<sup>2</sup>RT デバイスのWindows 8.1アクセス制御は、1 つの RT デバイスExchange ActiveSync。

<sup>3</sup>ユーザーのアクセスWindows 10には、Azure AD Premiumを含むサブスクリプションが必要で、デバイスをデバイスに参加Azure Active Directory。

> [!NOTE]
> 以前の OS バージョンで既に登録されているデバイスは引き続き機能しますが、機能は予告なしに変更される可能性があります。

組織内のユーザーが Basic Mobility and Security でサポートされていないモバイル デバイスを使用している場合は、Exchange ActiveSync アプリによるこれらのデバイスの Microsoft 365 メールへのアクセスをブロックして、組織のデータをより安全に保護することができます。 デバイスアクセスをブロックするExchange ActiveSync、「Basic Mobility and Security」の「デバイス アクセス[設定の管理」を参照してください](manage-device-access-settings.md)。

## <a name="access-control-for-microsoft-365-email-and-documents"></a>電子メールとドキュメントMicrosoft 365アクセス制御

次の表に示すさまざまな種類のモバイル デバイスでサポートされているアプリは、ユーザーのデバイスに適用される新しいモバイル デバイス管理ポリシーが作成され、ユーザーがデバイスを以前に登録しなかった場合に、Basic Mobility and Security に登録するようユーザーに求めるメッセージを表示します。 ポリシーの設定方法によっては、ユーザーのデバイスがポリシーに準拠しない場合、ユーザーがこれらのアプリの Microsoft 365 リソースにアクセスできないか、アクセス権を持っている可能性がありますが、Microsoft 365 はポリシー違反を報告します。

|**製品**|**iOS**|**Android**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSyncバージョン 14.1 以降を使用する組み込みの電子メールアプリとサードパーティ製アプリ (TouchDown など) が含Exchange ActiveSyncが含まれます。 |メール |電子メール |
| Office and  **OneDrive for Business** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**電話とタブレットの場合**:<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **電話のみ:** <br/> Office Mobile |

> [!NOTE]
>
> - iOS 10.0 以降のバージョンのサポートには、iPhoneデバイスiPad含まれます。
> - BlackBerry OS デバイスの管理は、Basic Security および Mobility ではサポートされていません。 BlackBerry の BlackBerry Business Cloud Services (BBCS) を使用して、BlackBerry OS デバイスを管理します。 Android OS を実行している Blackberry デバイスは、標準の Android デバイスとしてサポートされています
> - モバイル ブラウザーを使用して Microsoft 365 SharePoint サイト、Office Online のドキュメント、Outlook Web App の電子メールにアクセスする場合、ユーザーは登録を求めるメッセージが表示され、ポリシー違反に対してブロックまたは報告されません。

次の図は、新しいデバイスを持つユーザーが、Basic Mobility and Security によるアクセス制御をサポートするアプリにサインインした場合の処理を示しています。 ユーザーは、デバイスを登録するまでMicrosoft 365リソースへのアクセスをブロックされます。

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本的なモビリティとセキュリティ のアクセス制御。":::

> [!NOTE]
> Microsoft 365 Business Standard の基本モビリティとセキュリティで作成されたポリシーとアクセス ルールは、Exchange ActiveSync Exchange 管理センターで作成された Exchange ActiveSync モバイル デバイス メールボックス ポリシーとデバイス アクセス ルールを上書きします。 デバイスが Microsoft 365 Business Standard の Basic Mobility and Security に登録されると、Exchange ActiveSync に適用されたモバイル デバイス メールボックス ポリシーまたはデバイス アクセス ルールは無視されます。 詳細については、「Exchange ActiveSync」 [のExchange ActiveSyncを参照Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)。

## <a name="policy-settings-for-mobile-devices"></a>モバイル デバイス用のポリシー設定

特定の設定を有効にした状態でアクセスをブロックするポリシーを作成すると、[Microsoft 365](capabilities.md) の電子メールとドキュメントのアクセス制御に記載されているサポートされているアプリを使用している場合、ユーザーは Microsoft 365 リソースへのアクセスをブロックされます。

ユーザーがリソースにアクセスMicrosoft 365できる設定は、次のセクションに示されています。

- セキュリティ

- 暗号化

- 脱獄

- 管理された電子メール プロファイル

例として次の図は、登録済みデバイスを使用しているユーザーが、そのデバイスに適用されるモバイル デバイス管理ポリシーのセキュリティ設定を満たしていない場合の動作を示しています。 ユーザーは、Basic Mobility and Security を使用してアクセス制御をサポートするアプリにサインインします。 デバイスがセキュリティ設定に準拠するまでMicrosoft 365リソースへのアクセスがブロックされます。

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="基本的なモビリティとセキュリティのコンプライアンス メッセージ。":::

次のセクションでは、組織のリソースに接続するモバイル デバイスのセキュリティ保護と管理に使用できるポリシー Microsoft 365示します。

## <a name="security-settings"></a>セキュリティの設定

|**設定名**|**iOS** |**Android**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|パスワードを要求|はい|はい|はい|
|シンプルなパスワードを禁止|はい|いいえ|いいえ|
|英数字のパスワードを要求|はい|いいえ|いいえ|
|パスワードの最小文字数 |はい|はい|はい|
|デバイスがワイプされるまでのサインイン失敗回数 |はい|はい|はい|
|デバイスがロックされるまでのアイドル時間 (分) |はい|はい|はい|
|パスワードの有効期限 (日) |はい|はい|はい|
|パスワードの履歴を記憶して再利用を防止 |はい|はい|はい|

## <a name="encryption-settings"></a>暗号化の設定

|**設定名**|**iOS** |**Android**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|デバイスでデータ暗号化を要求<sup>する1</sup> |いいえ|はい|はい|

<sup>1</sup>Samsung Knox を使用すると、ストレージ カードで暗号化を要求できます。

## <a name="jail-broken-setting"></a>脱獄の設定

|**設定名**|**iOS** |**Android**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|デバイスの脱獄またはルート化はできません |はい|はい|はい|

## <a name="managed-email-profile-option"></a>管理された電子メール プロファイルのオプション

次のオプションは、手動で作成したメール プロファイルを使用しているMicrosoft 365ユーザーが自分のメールにアクセスするのをブロックできます。 iOS デバイスを使用しているユーザーは、電子メールにアクセスする前に、手動で作成した電子メール プロファイルを削除しておく必要があります。 プロファイルを削除すると、新しいプロファイルがデバイスに自動的に作成されます。 エンド ユーザーが準拠を取得する方法については、「既存の電子メール アカウントが見つかりました [」を参照してください](/intune-user-help/existing-company-email-account-found)。

|**設定名**|**iOS** |**Android**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|電子メール プロファイルが管理されている |はい|いいえ|いいえ|

## <a name="cloud-settings"></a>クラウドの設定

|**設定名**|**iOS** |**Android**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|暗号化されたバックアップを要求 |はい|いいえ|いいえ|
|クラウド バックアップの禁止 |はい|いいえ|いいえ|
|ドキュメントの同期の禁止 |はい|いいえ|いいえ|
|写真の同期の禁止  |はい|いいえ|いいえ|
|Google バックアップを許可する  |該当なし|いいえ|はい|
|Google アカウントの自動同期を許可する  |該当なし|いいえ|はい|

## <a name="system-settings"></a>システムの設定

|**設定名**|**iOS** |**Android**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|画面キャプチャの禁止 |はい|いいえ|はい|
|デバイスからの診断データ送信の禁止 |はい|いいえ|はい|

## <a name="application-settings"></a>アプリケーションの設定

|**設定名**|**iOS** |**Android**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|デバイスでのビデオ会議をブロックする |はい|いいえ|いいえ|
|アプリケーション ストアへのアクセスをブロックする |はい|いいえ|はい|
|アプリケーション ストアへアクセスする際にパスワードを要求する |いいえ|はい|はい|

## <a name="device-capabilities-settings"></a>デバイスの機能の設定

|**設定名**|**iOS** |**Android**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|リムーバブル記憶域との接続の禁止 |はい|はい|いいえ|
|Bluetooth 接続の禁止 |はい|はい|いいえ|

## <a name="additional-settings"></a>その他の設定

コンプライアンス センター PowerShell コマンドレットを使用して、次の&ポリシー設定を設定できます。 詳細については、「 [Security & コンプライアンス センター PowerShell」を参照してください](/powershell/exchange/scc-powershell)。

|**設定名**|**iOS** |**Android**|
|:-----|:-----|:-----|
|CameraEnabled|はい|はい|
|RegionRatings|はい|いいえ|
|MoviesRatings|はい|いいえ|
|TVShowsRating |はい|いいえ|
|AppsRatings |はい|いいえ|
|AllowVoiceDialing |はい|いいえ|
|AllowVoiceAssistant |はい|いいえ|
|AllowAssistantWhileLocked  |はい|いいえ|
|AllowPassbookWhileLocked |はい|いいえ|
|MaxPasswordGracePeriod |はい|いいえ|
|PasswordQuality |いいえ|はい|
|SystemSecurityTLS  |はい|いいえ|
|WLANEnabled  |いいえ|いいえ|

## <a name="settings-supported-by-windows"></a>設定によってサポートWindows

モバイル デバイスとして登録Windows 10デバイスを管理できます。 該当するポリシーが展開された後、Windows 10 デバイスを持つユーザーは、組み込みの電子メール アプリを初めて使用して Microsoft 365 メールにアクセスする際に 、Basic Mobility and Security に登録する必要があります (Azure AD プレミアム サブスクリプションが必要)。

次の設定は、モバイル Windows 10登録されているデバイスでサポートされます。 これらの設定では、ユーザーがリソースにアクセスMicrosoft 365は使用できない。

### <a name="security-settings"></a>セキュリティの設定

- 英数字のパスワードを要求

- パスワードの最小文字数

- デバイスがワイプされるまでのサインイン失敗回数

- デバイスがロックされるまでのアイドル時間 (分)

- パスワードの有効期限 (日)

- パスワードの履歴を記憶して再利用を防止

> [!NOTE]
> パスワードを調整する次の設定では、ローカル アカウントWindows制御します。 Windowsまたはドメインに参加して提供Azure Active Directoryアカウントは、これらの設定の影響を受け取らない。

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

デバイスが紛失または盗難に遭った場合は、機密の組織データを削除し、セキュリティ & コンプライアンス センター >  >  データ損失防止 **Device** 管理からワイプを実行することで、Microsoft 365 組織リソースへのアクセスを防止できます。 個別のワイプで組織のデータのみを削除することも、全体のワイプでデバイスからすべての情報を削除して出荷時の設定に戻すこともできます。

詳細については、「Basic  [Mobility and Security」の「モバイル デバイスのWipe」を参照してください](wipe-mobile-device.md)。

## <a name="related-content"></a>関連コンテンツ

[基本モビリティとセキュリティの概要 (](overview.md)Microsoft 365)\
[Basic Mobility and Security でデバイス セキュリティ ポリシーを作成する](create-device-security-policies.md) (記事)
