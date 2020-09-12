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
description: 基本的なモビリティとセキュリティは、モバイルデバイスをセキュリティで保護し、管理するのに役立ちます。
ms.openlocfilehash: aed4f4c2d252e487d24496ac00f3de24bc57ab55
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545898"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>基本的なモビリティとセキュリティの機能

基本的なモビリティとセキュリティは、組織内のライセンスである Microsoft 365 ユーザーが使用する iPhones、Ipad、Androids、Windows Phone などのモバイルデバイスをセキュリティで保護し、管理するのに役立ちます。 サポートされているモバイルデバイスおよびアプリについて、組織の Microsoft 365 電子メールおよびドキュメントへのアクセスを制御するのに役立つ設定を使用して、モバイルデバイス管理ポリシーを作成することができます。 デバイスの紛失または盗難時には、リモートからデバイスをワイプして、組織の機密情報を削除できます。

## <a name="supported-devices"></a>サポート対象のデバイス

基本的なモビリティとセキュリティを使用して、以下のデバイスをセキュリティで保護し、管理することができます。

- iOS 11.0 以降のバージョン
    
- Android 5.0 以降のバージョン<sup>3</sup>
    
- Windows 8.1<sup>1</sup>
    
- Windows 8.1 RT<sup>1</sup>
    
- Windows 10<sup>2</sup>
    
- Windows 10 Mobile<sup>2</sup>   

<sup>1</sup>Windows 8.1 RT デバイスのアクセス制御は、Exchange ActiveSync に限定されます。

<sup>2</sup>Windows 8.1 RT デバイスのアクセス制御は、Exchange ActiveSync に限定されます。
Windows 10 のアクセス制御には、Azure AD Premium を含むサブスクリプションが必要です。また、デバイスを Azure Active Directory に参加させる必要があります。

<sup>3</sup>Windows 8.1 RT デバイスのアクセス制御は、Exchange ActiveSync に限定されます。
2020年6月以降、2010バージョン9より後のバージョンでは、Samsung Knox デバイス以外のパスワード設定を管理できません。

>[!NOTE]
>以前のバージョンの OS で既に登録されているデバイスは、機能は予告なしに変更されることがありますが、引き続き機能します。

組織内のユーザーが基本的なモビリティとセキュリティでサポートされていないモバイルデバイスを使用している場合、組織のデータのセキュリティを強化するために、これらのデバイスの Microsoft 365 電子メールへの Exchange ActiveSync アプリのアクセスをブロックすることをお勧めします。 Exchange ActiveSync をブロックする手順については、「 [基本的なモビリティとセキュリティでデバイスアクセス設定を管理](manage-device-access-settings.md)する」を参照してください。

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Microsoft 365 メールとドキュメントのアクセス制御

次の表に示すさまざまな種類のモバイルデバイス用にサポートされているアプリは、ユーザーのデバイスに適用され、ユーザーが以前にデバイスを登録していない新しいモバイルデバイス管理ポリシーがある場合に、基本的なモビリティとセキュリティに登録するようにユーザーに促します。 ユーザーのデバイスがポリシーに準拠していない場合、ポリシーの設定方法によっては、ユーザーがこれらのアプリで Microsoft 365 リソースへのアクセスをブロックされたり、Microsoft 365 がポリシー違反を報告したりすることがあります。

|**製品**|**iOS 10.0 以降**|**Android 5.0 以降**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync には、Exchange ActiveSync バージョン14.1 以降を使用する、組み込みの電子メールとサードパーティ製のアプリ (接地など) が含まれています。 |メール |メール |
|**Office**  および **OneDrive For business** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**電話とタブレットの**場合:<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **電話のみ:** <br/> Office Mobile |

>[!NOTE]
- >IOS 10.0 以降のバージョンのサポートには、iPhone と iPad デバイスが含まれています。
- >Microsoft 365 のモバイルデバイス管理では、BlackBerry OS デバイスの管理はサポートされていません。 Blackberry のビジネスクラウドサービス (BBCS) を blackberry で使用して BlackBerry OS デバイスを管理します。 Android OS を実行している Blackberry デバイスは標準の Android デバイスとしてサポートされています。
- >ユーザーがモバイルブラウザーを使用して Microsoft 365 SharePoint サイト、Office Online 内のドキュメント、または Outlook Web App 内の電子メールにアクセスした場合、登録を求めるメッセージは表示されず、ブロックされたり、ポリシー違反が報告されることはありません。
    
次の図は、新しいデバイスを使用しているユーザーが、基本的なモビリティとセキュリティでアクセス制御をサポートするアプリにサインインしたときの動作を示しています。 ユーザーは、デバイスを登録するまで、アプリで Microsoft 365 リソースへのアクセスをブロックされます。

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本的なモビリティおよびセキュリティアクセス制御":::

注: Microsoft 365 Business Standard 用 MDM で作成されるポリシーとアクセスルールは、exchange ActiveSync モバイルデバイスメールボックスポリシーと、Exchange 管理センターで作成されたデバイスアクセスルールより優先されます。 Microsoft 365 Business Standard の MDM にデバイスを登録した後、デバイスに適用された Exchange ActiveSync モバイルデバイスメールボックスポリシーまたはデバイスアクセスルールは無視されます。 Exchange ActiveSync の詳細については、「exchange [activesync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380)」を参照してください。

## <a name="policy-settings-for-mobile-devices"></a>モバイル デバイス用のポリシー設定

特定の設定を有効にしてアクセスをブロックするポリシーを作成した場合、 [microsoft 365 の電子メールとドキュメントのアクセス制御](capabilities.md)に記載されているサポートされているアプリを使用すると、ユーザーは microsoft 365 リソースへのアクセスをブロックされます。 

ユーザーが Microsoft 365 リソースにアクセスできないようにする設定については、次のセクションを参照してください。

- セキュリティ
    
- 暗号化
    
- 脱獄
    
- 管理された電子メール プロファイル  

例として次の図は、登録済みデバイスを使用しているユーザーが、そのデバイスに適用されるモバイル デバイス管理ポリシーのセキュリティ設定を満たしていない場合の動作を示しています。 ユーザーは、基本的なモビリティとセキュリティでアクセス制御をサポートするアプリにサインインします。 デバイスがセキュリティ設定に準拠するまで、アプリ内の Microsoft 365 リソースへのアクセスはブロックされます。

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="基本的なモビリティおよびセキュリティコンプライアンスメッセージ":::

次のセクションでは、Microsoft 365 組織のリソースに接続するモバイルデバイスをセキュリティで保護し、管理するために使用できるポリシー設定を示します。

## <a name="security-settings"></a>セキュリティの設定

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|パスワードを要求|はい|はい|はい|
|シンプルなパスワードを禁止|はい|不要|不要|
|英数字のパスワードを要求|はい|不要|不要|
|パスワードの最小文字数 |はい|はい|はい|
|デバイスがワイプされるまでのサインイン失敗回数 |はい|はい|はい|
|デバイスがロックされるまでのアイドル時間 (分) |はい|はい|はい|
|パスワードの有効期限 (日) |はい|はい|はい|
|パスワードの履歴を記憶して再利用を防止 |はい|はい|はい|

## <a name="encryption-settings"></a>暗号化の設定 

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|デバイス<sup>1</sup>でデータの暗号化を必須にする |不要|はい|はい|

<sup>1</sup>Samsung Knox では、ストレージカードの暗号化も要求できます。 

## <a name="jail-broken-setting"></a>脱獄の設定 

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|デバイスの脱獄またはルート化はできません |はい|はい|はい|

## <a name="managed-email-profile-option"></a>管理された電子メール プロファイルのオプション 

次のオプションを使用すると、ユーザーが手動で作成した電子メールプロファイルを使用している場合に、ユーザーが Microsoft 365 メールにアクセスするのをブロックできます。 iOS デバイスを使用しているユーザーは、電子メールにアクセスする前に、手動で作成した電子メール プロファイルを削除しておく必要があります。 プロファイルを削除した後、新しいプロファイルがデバイスに自動的に作成されます。 エンドユーザーが準拠できる方法については、「 [既存の電子メールアカウントが見つかりました](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)。」を参照してください。

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|電子メール プロファイルが管理されている |はい|不要|不要|

## <a name="cloud-settings"></a>クラウドの設定 

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|暗号化されたバックアップを要求 |はい|不要|不要|
|クラウド バックアップの禁止 |はい|不要|不要|
|ドキュメントの同期の禁止 |はい|不要|不要|
|写真の同期の禁止  |はい|不要|不要|
|Google バックアップを許可する  |該当なし|いいえ|はい|
|Google アカウントの自動同期を許可する  |該当なし|いいえ|はい|

## <a name="system-settings"></a>システムの設定 

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|画面キャプチャの禁止 |はい|不要|はい|
|デバイスからの診断データ送信の禁止 |はい|不要|はい|

## <a name="application-settings"></a>アプリケーションの設定 

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|デバイスでのビデオ会議をブロックする |はい|不要|不要|
|アプリケーション ストアへのアクセスをブロックする |はい|不要|はい|
|アプリケーション ストアへアクセスする際にパスワードを要求する |不要|はい|はい|

## <a name="device-capabilities-settings"></a>デバイスの機能の設定 

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|リムーバブル記憶域との接続の禁止 |はい|はい|不要|
|Bluetooth 接続の禁止 |はい|はい|不要|

## <a name="additional-settings"></a>その他の設定

セキュリティ & コンプライアンスセンターの PowerShell コマンドレットを使用して、次の追加のポリシー設定を設定できます。 詳細については、「 [Security & コンプライアンスセンター PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell)」を参照してください。

|**設定名**|**iOS 7.1 以降**|**Android 5 以降**|
|:-----|:-----|:-----|
|CameraEnabled|はい|はい|
|RegionRatings|はい|不要|
|MoviesRatings|はい|不要|
|TVShowsRating |はい|不要|
|AppsRatings |はい|不要|
|AllowVoiceDialing |はい|不要|
|AllowVoiceAssistant |はい|不要|
|AllowAssistantWhileLocked  |はい|不要|
|Allowpass Booklocked Locked |はい|不要|
|MaxPasswordGracePeriod |はい|不要|
|PasswordQuality |不要|はい|
|SystemSecurityTLS  |はい|不要|
|WLANEnabled  |不要|不要|

## <a name="settings-supported-by-windows"></a>Windows でサポートされている設定 

Windows 10 デバイスは、モバイルデバイスとして登録することによって管理できます。 適用可能なポリシーを展開した後、Windows 10 デバイスを使用しているユーザーは、組み込みの電子メールアプリを使用して Microsoft 365 メールにアクセスするときに、基本的なモビリティとセキュリティに登録する必要があります (Azure AD premium サブスクリプションを必要とします)。

次の設定は、モバイルデバイスとして登録されている Windows 10 デバイスでサポートされています。 これらの設定は、ユーザーが Microsoft 365 リソースにアクセスすることをブロックしません。

### <a name="security-settings"></a>セキュリティの設定

- 英数字のパスワードを要求

- パスワードの最小文字数
    
- デバイスがワイプされるまでのサインイン失敗回数
    
- デバイスがロックされるまでのアイドル時間 (分)
    
- パスワードの有効期限 (日)
    
- パスワードの履歴を記憶して再利用を防止   

>[!NOTE]
>次の設定は、パスワードを制御するローカル Windows アカウントのみを制御します。 ドメインまたは Azure Active Directory に参加して提供された Windows アカウントは、これらの設定の影響を受けません。

### <a name="system-settings"></a>システムの設定

デバイスから診断データを送信することを禁止します。

### <a name="additional-settings"></a>その他の設定

PowerShell コマンドレットを使用して、これらの追加のポリシー設定を行うことができます。

- AllowConvenienceLogon
    
- UserAccountControlStatus
    
- FirewallStatus
    
- AutoUpdateStatus
    
- AntiVirusStatus   

- AntiVirusSignatureStatus
    
- SmartScreenEnabled
    
- WorkFoldersSyncUrl
    

## <a name="remotely-wipe-a-mobile-device"></a>モバイル デバイスをリモートからワイプする

デバイスが紛失または盗難にあった場合は、機密の組織データを削除し、セキュリティ & コンプライアンスセンター >**データ損失防止**  >  **デバイス管理**からのワイプを行って、Microsoft 365 組織のリソースにアクセスできないようにすることができます。 個別のワイプで組織のデータのみを削除することも、全体のワイプでデバイスからすべての情報を削除して出荷時の設定に戻すこともできます。

詳細については、「 [Basic Mobility And Security でモバイルデバイスをワイプする](wipe-mobile-device.md)」を参照してください。

## <a name="related-topics"></a>関連トピック

[Microsoft 365 の基本的なモビリティとセキュリティの概要](overview.md)

[基本的なモビリティとセキュリティでデバイスのセキュリティポリシーを作成する](create-device-security-policies.md)