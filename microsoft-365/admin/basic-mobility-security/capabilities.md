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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 基本的なモビリティとセキュリティは、モバイル デバイスのセキュリティ保護と管理に役立ちます。
ms.openlocfilehash: 60de4e3f36427a69ecf0bf52e5dfd34f089991f3
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994975"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>基本的なモビリティとセキュリティの機能

Basic Mobility and Security は、組織内のライセンスを取得した Microsoft 365 ユーザーが使用する iPhone、iPad、Android、Windows Phone など、モバイル デバイスのセキュリティ保護と管理に役立ちます。 組織の Microsoft 365 メールへのアクセスを制御するのに役立つ設定と、サポートされているモバイル デバイスとアプリのドキュメントを使用して、モバイル デバイス管理ポリシーを作成できます。 デバイスの紛失または盗難時には、リモートからデバイスをワイプして、組織の機密情報を削除できます。

## <a name="supported-devices"></a>サポート対象のデバイス

Basic Mobility and Security を使用すると、次のデバイスをセキュリティで保護および管理できます。

- iOS 11.0 以降のバージョン

- Android 5.0 以降のバージョン<sup>3</sup>

- Windows 8.1<sup>1</sup>

- Windows 8.1 RT<sup>1</sup>

- Windows 10<sup>2</sup>

- Windows 10 Mobile<sup>2</sup>

<sup>1</sup>Windows 8.1 RT デバイスのアクセス制御は、1 つの RT デバイスExchange ActiveSync。

<sup>2</sup>Windows 10 のアクセス制御には、Azure AD Premium を含むサブスクリプションが必要で、デバイスを Azure Active Directory に参加する必要があります。

<sup>3</sup>2020 年 6 月以降、9 より後の Android バージョンでは、Samsung Knox デバイス以外のパスワード設定を管理できません。

>[!NOTE]
>以前の OS バージョンで既に登録されているデバイスは引き続き機能しますが、機能は予告なしに変更される可能性があります。

組織内のユーザーが基本モビリティとセキュリティでサポートされていないモバイル デバイスを使用している場合は、組織のデータをより安全にするために、これらのデバイスの Microsoft 365 メールへの Exchange ActiveSync アプリアクセスをブロックできます。 デバイスアクセスをブロックするExchange ActiveSync、「Basic Mobility and Security」の「デバイス アクセス設定の [管理」を参照してください](manage-device-access-settings.md)。

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Microsoft 365 の電子メールとドキュメントのアクセス制御

次の表に示すさまざまな種類のモバイル デバイスでサポートされているアプリは、ユーザーのデバイスに適用される新しいモバイル デバイス管理ポリシーが作成され、ユーザーがデバイスを以前に登録しなかった場合に、Basic Mobility and Security に登録するようユーザーに求めるメッセージを表示します。 ポリシーの設定方法によっては、ユーザーのデバイスがポリシーに準拠しない場合、ユーザーがこれらのアプリの Microsoft 365 リソースにアクセスできないか、アクセス権を持っている可能性がありますが、Microsoft 365 はポリシー違反を報告します。

|**Product**|**iOS 10.0 以降**|**Android 5.0 以降**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSyncには、バージョン 14.1 以降を使用する組み込みの電子メールアプリと、TouchDown Exchange ActiveSyncサード パーティ製アプリが含まれます。 |メール |メール |
|**Office**   **および OneDrive for Business** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**電話とタブレットの場合**:<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **電話のみ:** <br/> Office Mobile |

>[!NOTE]
- >iOS 10.0 以降のバージョンのサポートには、iPhone デバイスと iPad デバイスが含まれます。
- >BlackBerry OS デバイスの管理は、Basic Security および Mobility ではサポートされていません。 BlackBerry の BlackBerry Business Cloud Services (BBCS) を使用して、BlackBerry OS デバイスを管理します。 Android OS を実行している Blackberry デバイスは、標準の Android デバイスとしてサポートされています
- >モバイル ブラウザーを使用して Microsoft 365 SharePoint サイト、Office Online のドキュメント、または Outlook Web App の電子メールにアクセスする場合、ユーザーは登録を求めるメッセージが表示され、ポリシー違反に対してブロックまたは報告されません。

次の図は、新しいデバイスを持つユーザーが、Basic Mobility and Security によるアクセス制御をサポートするアプリにサインインした場合の処理を示しています。 ユーザーがデバイスを登録するまで、アプリ内の Microsoft 365 リソースへのアクセスがブロックされます。

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本的なモビリティとセキュリティ アクセス制御":::

> [!NOTE]
> Microsoft 365 Business Standard の Basic Mobility and Security で作成されたポリシーとアクセス ルールは、Exchange 管理センターで作成された Exchange ActiveSync モバイル デバイス メールボックス ポリシーとデバイス アクセス ルールを上書きします。 デバイスが Microsoft 365 Business Standard の Basic Mobility and Security に登録されると、デバイスに適用される Exchange ActiveSync モバイル デバイス メールボックス ポリシーまたはデバイス アクセス ルールは無視されます。 このページの詳細については、「Exchange ActiveSync Exchange [Online Exchange ActiveSync」を参照してください](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)。

## <a name="policy-settings-for-mobile-devices"></a>モバイル デバイス用のポリシー設定

特定の設定を有効にした状態でアクセスをブロックするポリシーを作成すると [、Microsoft 365](capabilities.md)の電子メールとドキュメントのアクセス制御に記載されているサポートされているアプリを使用すると、ユーザーは Microsoft 365 リソースへのアクセスをブロックされます。 

ユーザーが Microsoft 365 リソースにアクセスをブロックできる設定は、次のセクションに示されています。

- セキュリティ

- 暗号化

- 脱獄

- 管理された電子メール プロファイル  

例として次の図は、登録済みデバイスを使用しているユーザーが、そのデバイスに適用されるモバイル デバイス管理ポリシーのセキュリティ設定を満たしていない場合の動作を示しています。 ユーザーは、Basic Mobility and Security を使用してアクセス制御をサポートするアプリにサインインします。 デバイスがセキュリティ設定に準拠するまで、アプリ内の Microsoft 365 リソースへのアクセスがブロックされます。

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Basic Mobility and Security compliance message":::

次のセクションでは、Microsoft 365 組織リソースに接続するモバイル デバイスのセキュリティ保護と管理に使用できるポリシー設定を示します。

## <a name="security-settings"></a>セキュリティの設定

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|**Samsung Knox**|
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

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|デバイスでデータ暗号化を要求<sup>する 1</sup> |いいえ|はい|はい|

<sup>1</sup>Samsung Knox を使用すると、ストレージ カードで暗号化を要求できます。 

## <a name="jail-broken-setting"></a>脱獄の設定 

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|デバイスの脱獄またはルート化はできません |はい|はい|はい|

## <a name="managed-email-profile-option"></a>管理された電子メール プロファイルのオプション 

次のオプションは、手動で作成したメール プロファイルを使用している場合、ユーザーが Microsoft 365 メールにアクセスできません。 iOS デバイスを使用しているユーザーは、電子メールにアクセスする前に、手動で作成した電子メール プロファイルを削除しておく必要があります。 プロファイルを削除すると、新しいプロファイルがデバイスに自動的に作成されます。 エンド ユーザーが準拠を取得する方法については、「既存の電子メール アカウントが見つかりました [」を参照してください](/intune-user-help/existing-company-email-account-found)。

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|電子メール プロファイルが管理されている |はい|いいえ|いいえ|

## <a name="cloud-settings"></a>クラウドの設定

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|暗号化されたバックアップを要求 |はい|いいえ|いいえ|
|クラウド バックアップの禁止 |はい|いいえ|いいえ|
|ドキュメントの同期の禁止 |はい|いいえ|いいえ|
|写真の同期の禁止  |はい|いいえ|いいえ|
|Google バックアップを許可する  |該当なし|いいえ|はい|
|Google アカウントの自動同期を許可する  |該当なし|いいえ|はい|

## <a name="system-settings"></a>システムの設定

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|画面キャプチャの禁止 |はい|いいえ|はい|
|デバイスからの診断データ送信の禁止 |はい|いいえ|はい|

## <a name="application-settings"></a>アプリケーションの設定

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|デバイスでのビデオ会議をブロックする |はい|いいえ|いいえ|
|アプリケーション ストアへのアクセスをブロックする |はい|いいえ|はい|
|アプリケーション ストアへアクセスする際にパスワードを要求する |いいえ|はい|はい|

## <a name="device-capabilities-settings"></a>デバイスの機能の設定

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|リムーバブル記憶域との接続の禁止 |はい|はい|いいえ|
|Bluetooth 接続の禁止 |はい|はい|いいえ|

## <a name="additional-settings"></a>その他の設定

コンプライアンス センター PowerShell コマンドレットを使用して、次の&ポリシー設定を設定できます。 詳細については、「Security [& コンプライアンス センター PowerShell」を参照してください](/powershell/exchange/scc-powershell)。

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|
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

## <a name="settings-supported-by-windows"></a>Windows でサポートされる設定

Windows 10 デバイスは、モバイル デバイスとして登録することで管理できます。 該当するポリシーが展開された後、Windows 10 デバイスを使用するユーザーは、組み込みの電子メール アプリを初めて使用して Microsoft 365 メールにアクセスする際に、Basic Mobility and Security に登録する必要があります (Azure AD プレミアム サブスクリプションが必要です)。

モバイル デバイスとして登録されている Windows 10 デバイスでは、次の設定がサポートされています。 これらの設定では、ユーザーが Microsoft 365 リソースにアクセスできない場合があります。

### <a name="security-settings"></a>セキュリティの設定

- 英数字のパスワードを要求

- パスワードの最小文字数

- デバイスがワイプされるまでのサインイン失敗回数

- デバイスがロックされるまでのアイドル時間 (分)

- パスワードの有効期限 (日)

- パスワードの履歴を記憶して再利用を防止

>[!NOTE]
>パスワードを調整する次の設定では、ローカル Windows アカウントのみを制御します。 ドメインまたは Azure Active Directory に参加して提供される Windows アカウントは、これらの設定の影響を受け取らない。

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

デバイスが紛失または盗難に遭った場合は、機密の組織データを削除し、セキュリティ & コンプライアンス センター > データ損失防止デバイス管理からワイプを行って、Microsoft 365 組織リソースへのアクセスを防止できます。   >   個別のワイプで組織のデータのみを削除することも、全体のワイプでデバイスからすべての情報を削除して出荷時の設定に戻すこともできます。

詳細については、「Basic [Mobility and Security」でモバイル デバイスをワイプするを参照してください](wipe-mobile-device.md)。

## <a name="related-topics"></a>関連項目

[Microsoft 365 の基本モビリティとセキュリティの概要](overview.md)

[Basic Mobility and Security でデバイス セキュリティ ポリシーを作成する](create-device-security-policies.md)