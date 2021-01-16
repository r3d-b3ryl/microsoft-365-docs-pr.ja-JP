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
ms.openlocfilehash: 746131e90e207d7b888a3ddcaf4ff0656606a2c7
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877118"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>基本的なモビリティとセキュリティの機能

Basic Mobility and Security は、組織内のライセンスを取得した Microsoft 365 ユーザーが使用する iPhone、iPad、Android、Windows Phone など、モバイル デバイスのセキュリティ保護と管理に役立ちます。 サポートされているモバイル デバイスとアプリの組織の Microsoft 365 電子メールとドキュメントへのアクセスを制御できる設定を使用して、モバイル デバイス管理ポリシーを作成できます。 デバイスの紛失または盗難時には、リモートからデバイスをワイプして、組織の機密情報を削除できます。

## <a name="supported-devices"></a>サポート対象のデバイス

Basic Mobility and Security を使用して、次のデバイスをセキュリティで保護および管理できます。

- iOS 11.0 以降のバージョン

- Android 5.0 以降のバージョン<sup>3</sup>

- Windows 8.1<sup>1</sup>

- Windows 8.1 RT<sup>1</sup>

- Windows 10<sup>2</sup>

- Windows 10 Mobile<sup>2</sup>

<sup>1</sup>Windows 8.1 RT デバイスのアクセス制御は、次の制限Exchange ActiveSync。

<sup>2</sup>Windows 8.1 RT デバイスのアクセス制御は、次の制限Exchange ActiveSync。
Windows 10 のアクセス制御には、Azure AD Premium を含み、デバイスを Azure Active Directory に参加する必要があるサブスクリプションが必要です。

<sup>3</sup>Windows 8.1 RT デバイスのアクセス制御は、次の制限Exchange ActiveSync。
2020 年 6 月以降、9 より後の Android バージョンでは、Samsung Knox デバイス以外のパスワード設定を管理できません。

>[!NOTE]
>以前の OS バージョンで既に登録されているデバイスは引き続き機能しますが、機能は予告なしに変更される可能性があります。

Basic Mobility and Security でサポートされていないモバイル デバイスを組織内のユーザーが使用している場合は、組織のデータのセキュリティを強化するために、それらのデバイスの Microsoft 365 メールへの Exchange ActiveSync アプリのアクセスをブロックできます。 デバイスアクセスをブロックする手順Exchange ActiveSync Basic Mobility and Security のデバイス アクセス設定の管理に関する [ページを参照してください](manage-device-access-settings.md)。

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Microsoft 365 のメールとドキュメントのアクセス制御

次の表に示すさまざまな種類のモバイル デバイスでサポートされているアプリは、ユーザーのデバイスに適用される新しいモバイル デバイス管理ポリシーが作成され、ユーザーがデバイスを以前に登録しなかった場合に、Basic Mobility and Security に登録するように求めるメッセージをユーザーに表示します。 ユーザーのデバイスがポリシーに準拠しない場合、ポリシーの設定方法によっては、ユーザーがこれらのアプリの Microsoft 365 リソースにアクセスできないか、アクセス権を持っている可能性がありますが、Microsoft 365 はポリシー違反を報告します。

|**Product**|**iOS 10.0 以降**|**Android 5.0 以降**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSyncには、TouchDown など、組み込みのメールアプリや、Exchange ActiveSync Version 14.1 以降を使用するサード パーティ製アプリが含まれています。 |メール |メール |
|**Office**   **OneDrive for Business** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**電話とタブレットの場合**:<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **電話のみ:** <br/> Office Mobile |

>[!NOTE]
- >iOS 10.0 以降のバージョンのサポートには、iPhone および iPad デバイスが含まれます。
- >BlackBerry OS デバイスの管理は、基本セキュリティとモビリティではサポートされていません。 BlackBerry の BlackBerry Business Cloud Services (BBS) を使用して、BlackBerry OS デバイスを管理します。 Android OS を実行している Blackberry デバイスは、標準の Android デバイスとしてサポートされています
- >モバイル ブラウザーを使用して Microsoft 365 SharePoint サイト、Office Online のドキュメント、または Outlook Web App の電子メールにアクセスした場合、ユーザーは登録を求めるメッセージが表示されません。また、ポリシー違反がブロックまたは報告されません。

次の図は、新しいデバイスを持つユーザーが、Basic Mobility and Security によるアクセス制御をサポートするアプリにサインインした場合の処理を示しています。 ユーザーは、デバイスを登録するまで、アプリ内の Microsoft 365 リソースへのアクセスをブロックされます。

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本的なモビリティとセキュリティのアクセス制御":::

> [!NOTE]
> Microsoft 365 Business Standard の Basic Mobility and Security で作成されたポリシーとアクセス ルールは、Exchange 管理センターで作成された Exchange ActiveSync モバイル デバイス メールボックス ポリシーとデバイス アクセス ルールより優先されます。 デバイスを Microsoft 365 Business Standard の Basic Mobility and Security に登録すると、そのデバイスに適用される Exchange ActiveSync モバイル デバイス メールボックス ポリシーまたはデバイス アクセス ルールは無視されます。 Exchange Online の詳細については、「Exchange ActiveSync」 [をExchange ActiveSync覧ください](https://go.microsoft.com/fwlink/p/?LinkId=524380)。

## <a name="policy-settings-for-mobile-devices"></a>モバイル デバイス用のポリシー設定

特定の設定を有効にした状態でアクセスをブロックするポリシーを作成すると、Microsoft 365 のメールとドキュメントのアクセス制御に記載されているサポートされているアプリを使用すると、ユーザーは [Microsoft 365](capabilities.md)リソースへのアクセスをブロックされます。 

ユーザーが Microsoft 365 リソースにアクセスするのをブロックできる設定については、次のセクションを参照してください。

- セキュリティ

- 暗号化

- 脱獄

- 管理された電子メール プロファイル  

例として次の図は、登録済みデバイスを使用しているユーザーが、そのデバイスに適用されるモバイル デバイス管理ポリシーのセキュリティ設定を満たしていない場合の動作を示しています。 ユーザーは、Basic Mobility and Security によるアクセス制御をサポートするアプリにサインインします。 デバイスがセキュリティ設定に準拠するまで、アプリ内の Microsoft 365 リソースへのアクセスはブロックされます。

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="基本的なモビリティとセキュリティのコンプライアンス メッセージ":::

以下のセクションでは、Microsoft 365 組織リソースに接続するモバイル デバイスのセキュリティ保護と管理に使用できるポリシー設定を示します。

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
|デバイス 1 でデータの暗号化を<sup>要求する</sup> |いいえ|はい|はい|

<sup>1</sup>Samsung Knox では、ストレージ カードの暗号化を要求できます。 

## <a name="jail-broken-setting"></a>脱獄の設定 

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|デバイスの脱獄またはルート化はできません |はい|はい|はい|

## <a name="managed-email-profile-option"></a>管理された電子メール プロファイルのオプション 

次のオプションでは、ユーザーが手動で作成したメール プロファイルを使用している場合、ユーザーが Microsoft 365 メールにアクセスできません。 iOS デバイスを使用しているユーザーは、電子メールにアクセスする前に、手動で作成した電子メール プロファイルを削除しておく必要があります。 プロファイルを削除すると、新しいプロファイルがデバイスに自動的に作成されます。 エンド ユーザーが準拠する方法については、「既存の電子メール アカウントが見つかりました」を [参照してください](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)。

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

セキュリティ センターとコンプライアンス センターの PowerShell コマンドレットを使用して、次&ポリシー設定を設定できます。 詳細については、「Security [& Compliance Center PowerShell」を参照してください](https://docs.microsoft.com/powershell/exchange/scc-powershell)。

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

## <a name="settings-supported-by-windows"></a>Windows でサポートされている設定

Windows 10 デバイスは、モバイル デバイスとして登録することで管理できます。 該当するポリシーを展開すると、Windows 10 デバイスを使用するユーザーは、組み込みの電子メール アプリを初めて使用して Microsoft 365 メールにアクセスする際に Basic Mobility and Security に登録する必要があります (Azure AD Premium サブスクリプションが必要)。

モバイル デバイスとして登録されている Windows 10 デバイスでは、次の設定がサポートされています。 これらの設定は、ユーザーが Microsoft 365 リソースにアクセスできないのをブロックする必要があります。

### <a name="security-settings"></a>セキュリティの設定

- 英数字のパスワードを要求

- パスワードの最小文字数

- デバイスがワイプされるまでのサインイン失敗回数

- デバイスがロックされるまでのアイドル時間 (分)

- パスワードの有効期限 (日)

- パスワードの履歴を記憶して再利用を防止

>[!NOTE]
>パスワードを使用する次の設定では、ローカルの Windows アカウントのみを制御します。 ドメインまたは Azure Active Directory への参加を通じて提供される Windows アカウントは、これらの設定の影響を受け取らない。

### <a name="system-settings"></a>システムの設定

デバイスからの診断データの送信をブロックします。

### <a name="additional-settings"></a>その他の設定

PowerShell コマンドレットを使用して、これらの追加のポリシー設定を設定できます。

- AllowConvenienceLogon

- UserAccountControlStatus

- FirewallStatus

- AutoUpdateStatus

- AntiVirusStatus

- AntiVirusSignatureStatus

- SmartScreenEnabled

- WorkFoldersSyncUrl

## <a name="remotely-wipe-a-mobile-device"></a>モバイル デバイスをリモートからワイプする

デバイスが紛失したり盗まれたりした場合は、セキュリティ & コンプライアンス センター > データ損失防止デバイス管理からワイプを実行することで、機密性の高い組織データを削除し、Microsoft 365 組織のリソースへのアクセスを防ぐのに役立ちます  >  。 個別のワイプで組織のデータのみを削除することも、全体のワイプでデバイスからすべての情報を削除して出荷時の設定に戻すこともできます。

詳細については [、「Basic Mobility and Security」の「モバイル デバイスをワイプする」を参照してください](wipe-mobile-device.md)。

## <a name="related-topics"></a>関連項目

[Microsoft 365 の基本的なモビリティとセキュリティの概要](overview.md)

[Basic Mobility and Security でのデバイス セキュリティ ポリシーの作成](create-device-security-policies.md)