---
title: Microsoft 365 のセッション タイムアウト
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: 37a5c116-5b07-4f70-8333-5b86fd2c3c40
ms.collection:
- M365-security-compliance
description: Microsoft 365 クライアント アプリのセキュリティと簡単なアクセスのバランスを取るセッション タイムアウトの使い方について説明します。
ms.openlocfilehash: b85ed8a45727e8a8eed2537fa2233125cd05ece7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924918"
---
# <a name="session-timeouts-for-microsoft-365"></a>Microsoft 365 のセッション タイムアウト

セッションの有効期間は、Microsoft 365 の認証の重要な部分であり、セキュリティのバランスを取る上で重要なコンポーネントであり、ユーザーに資格情報の入力を求める回数です。

## <a name="session-times-for-microsoft-365-services"></a>Microsoft 365 サービスのセッション時間

Microsoft 365 Web アプリまたはモバイル アプリでユーザーが認証されると、セッションが確立されます。 セッションの期間中、ユーザーは再認証する必要がなされます。 セッションの有効期限は、ユーザーが非アクティブな場合、ブラウザーまたはタブを閉じる場合、またはパスワードがリセットされた場合など、その他の理由で認証トークンが期限切れになった場合です。 Microsoft 365 サービスには、各サービスの一般的な使用に対応するセッション タイムアウトが異なります。

次の表に、Microsoft 365 サービスのセッションの有効期間を示します。

| Microsoft 365 サービス | セッション タイムアウト |
|:-----|:-----|
|Microsoft 365 管理センター  <br/> |管理センターの資格情報を 8 時間ごとに提供する必要があります。  <br/> |
|SharePoint Online  <br/> |ユーザーが [サインインし続ける] を選択している限り、5 **日間非アクティブです**。 ユーザーが前のサインインから 24 時間以上経過した後に再度 SharePoint Online にアクセスすると、タイムアウト値は 5 日にリセットされます。  <br/> |
|Outlook Web App  <br/> |6 時間。  <br/> この値は [、Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)コマンドレットの _ActivityBasedAuthenticationTimeoutInterval_ パラメーターを使用して変更できます。  <br/> |
|Azure Active Directory  <br/> (モダン認証がOffice Windows クライアントの Microsoft 365 アプリケーションで使用されます)  <br/> | 最新の認証では、アクセス トークンと更新トークンを使用して、Azure Active Directory を使用して Microsoft 365 リソースへのユーザー アクセスを許可します。 アクセス トークンは、認証が成功した後に提供される JSON Web トークンであり、1 時間有効です。 有効期間が長い更新トークンも提供されます。 アクセス トークンの有効期限が切れると、Officeクライアントは有効な更新トークンを使用して新しいアクセス トークンを取得します。 この交換は、ユーザーの初期認証がまだ有効な場合に成功します。  <br/>  更新トークンは 90 日間有効で、継続的に使用すると、失効するまで有効になります。  <br/>  更新トークンは、次のようないくつかのイベントによって無効にできます。  <br/>  更新トークンが発行された後、ユーザーのパスワードが変更されました。  <br/>  管理者は、ユーザーがアクセスしようとしているリソースへのアクセスを制限する条件付きアクセス ポリシーを適用できます。  <br/> |
|Android、iOS、および Windows 10 用の SharePoint および OneDrive モバイル アプリ  <br/> |アクセス トークンの既定の有効期間は 1 時間です。 更新トークンの既定の非アクティブ時間は 90 日です。  <br/> [トークンの詳細とトークンの有効期間を構成する方法](/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> 更新トークンを取り消す場合は、ユーザーの Microsoft 365 パスワードをリセットできます。  <br/> |
|Yammer Microsoft 365 Sign-In  <br/> |ブラウザーの有効期間。 ユーザーがブラウザーを閉じて新Yammerにアクセスすると、Yammer Microsoft 365 で再認証されます。 ユーザーが Cookie をキャッシュするサード パーティ製のブラウザーを使用する場合、ブラウザーを再び開く際に再認証する必要が生じない場合があります。  <br/> > [!NOTE]> これは、Microsoft 365 を使用するネットワークでのみ有効で、Sign-InにYammer。           |