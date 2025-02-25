---
title: 手順 7 - 元従業員のユーザー アカウントを削除する
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- m365solution-removeemployee
search.appverid:
- BCS160
- MET150
- MOE150
description: 元従業員のすべてのユーザー データを保存してアクセスしたら、Microsoft 365 管理センターで元従業員のアカウントを削除できます。
ms.openlocfilehash: 5a1929ef1a5ff26ee0e84993f0a7cabb5ebc4617
ms.sourcegitcommit: db1e48af88995193f15bbd5962f5101a6088074b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2022
ms.locfileid: "65636176"
---
# <a name="step-7---delete-a-former-employees-user-account"></a>手順 7 - 元従業員のユーザー アカウントを削除する

元従業員のすべてのユーザー データにアクセスして保存したら、元従業員のアカウントを削除できます。

> [!IMPORTANT]
> メールの転送を設定した場合や、アカウントを共有メールボックスに変換した場合、アカウントを削除しないでください。いずれの場合も、メール転送および共有メールボックスを固定するには、アカウントが必要です。

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。
2. 削除する従業員の名前を選択します。
3. ユーザーの名前の下で、[ **ユーザーの削除**] を選択します。 このユーザーに必要なオプションを選択し、[ユーザーの **削除**] を選択します。 このユーザーの電子メールとOneDriveに対する別のユーザー アクセス権を既に付与している場合は、ここでもう一度行う必要はありません。

ユーザーを削除するとき、約 30 日間アカウントが無効になります。 アカウントを完全に削除する前に、それまでアカウントを復元する必要があります。

## <a name="watch-delete-a-former-employees-user-account"></a>ウォッチ: 元従業員のユーザー アカウントを削除する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR]

このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](../../business-video/index.yml)」をご覧ください。

## <a name="does-your-organization-use-active-directory"></a>組織では Active Directory を使用していますか。

組織がユーザー アカウントをローカルの Active Directory 環境からMicrosoft 365に同期する場合は、ローカル Active Directory サービスでそれらのユーザー アカウントを削除して復元する必要があります。 ユーザー アカウントを Office 365 で削除または復元することはできません。

Active Directory でユーザー アカウントを削除して復元する方法については、「 [ユーザー アカウントの削除](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))」を参照してください。
  
Azure Active Directoryを使用している場合は、[Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell コマンドレットを参照してください。
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>従業員のメール セッションの終了について知っておく必要があること

ここでは、従業員のメールの使用を終了する方法について説明します (Exchange)。

<br>

****

|可能な操作|方法|
|:-----|:-----|
|セッション (Outlook on the web、Outlook、Exchange Active Sync など) を終了し、新しいセッションを強制的に開く|パスワードを再設定する|
|(すべてのプロトコルの) セッションを終了し、今後のセッションに対するアクセスをブロックする|アカウントを無効にする。 たとえば、Exchange管理センターで、または PowerShell を使用するとします。 <p>  `Set-Mailbox user@contoso.com -AccountDisabled:$true`|
|特定のプロトコル (ActiveSync など) のセッションを終了する|プロトコルを無効にする。 たとえば、Exchange管理センターで、または PowerShell を使用するとします。 <p>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false`|
|

上記の操作は、次の 3 つの場所で実行できます。
  
<br>

****

|セッションを終了する場所|所要時間|
|---|---|
|Exchange 管理センターまたは PowerShell を使用する場合|予想される遅延が 30 分以内|
|Azure Active Directory 管理センター|予想される遅延が 60 分以内|
|オンプレミス環境|予想される遅延が 3 時間以上|
|

### <a name="how-to-get-fastest-response-for-account-termination"></a>アカウントの終了に対して最も迅速な応答を取得する方法

**最も迅速な応答**: Exchange 管理センターを使用 (PowerShell を使用) するか、または Azure Active Directory 管理センターを使用します。オンプレミスの環境では、DirSync を介して変更を同期するのに数時間かかる場合があります。
  
**オンプレミスおよび Exchange データ センターにプレゼンスがあるユーザーの場合、迅速な応答**: Azure Active Directory 管理センター/Exchange 管理センターを使用してセッションを終了し、オンプレミスの環境でも変更を加えます。そうしないと、Azure Active Directory 管理センター/Exchange 管理センターでの変更は、DirSync によって上書きされます。
  
## <a name="related-content"></a>関連コンテンツ

[ユーザーを復元する](restore-user.md) (記事)

[パスワードをリセットする](reset-passwords.md) (記事)
