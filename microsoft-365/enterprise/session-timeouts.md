---
title: Microsoft 365 のセッション タイムアウト
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
ms.service: o365-administration
ms.localizationpriority: medium
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
description: セッション タイムアウトを使用して、Microsoft 365 クライアント アプリのセキュリティとアクセスのしやすさのバランスをとる方法を学びます。
ms.openlocfilehash: f5b7c87cabfd6f80061c2795568cd53955caa10f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213267"
---
# <a name="session-timeouts-for-microsoft-365"></a>Microsoft 365 のセッション タイムアウト

セッションの有効期間は、Microsoft 365 の認証の重要な部分で、またセキュリティと、ユーザーに資格情報の入力を求める回数のバランスを取るうえで重要なコンポーネントです。

## <a name="session-times-for-microsoft-365-services"></a>Microsoft 365 サービスのセッション時間

ユーザーが Microsoft 365 Web アプリまたはモバイル アプリのいずれかで認証すると、セッションが確立されます。 セッションの有効期間中、ユーザーは再認証を受ける必要はありません。 ブラウザーが非アクティブである場合、ユーザーがブラウザーまたはタブを閉じた場合、またはその他の理由でユーザーの認証トークンが期限切れになった場合は、セッションが期限切れになる可能性があります。 Microsoft 365 サービスの場合、各サービスの典型的な使用に対して、さまざまなセッション タイムアウトがあります。

次の表に、Microsoft 365 サービスのセッションの有効期間を示します。

| Microsoft 365 サービス | セッション タイムアウト |
|:-----|:-----|
|Microsoft 365 管理センター  <br/> |8 時間ごとに管理センターの資格情報を提供するように求められます。  <br/> |
|SharePoint Online  <br/> |ユーザーが [**サインアウトしない**] を選択している場合、5 日間非アクティブです。 前回のサインインから 24 時間以上が経過した後にユーザーが SharePoint Online に再度アクセスすると、タイムアウト値が 5 日にリセットされます。  <br/> |
|Outlook Web App  <br/> |6 時間。  <br/> この値は、[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) コマンドレットの _ActivityBasedAuthenticationTimeoutInterval_ パラメーターを使用して変更できます。  <br/> |
|Azure Active Directory  <br/> (最新の認証が有効になっている Windows クライアントの Office および Microsoft 365 アプリケーションで使用されます)  <br/> | 最新の認証では、アクセス トークンと更新トークンを使用して、Azure Active Directory を使用する Microsoft 365 リソースへのユーザー アクセスを許可します。 アクセス トークンは、認証が成功した後に提供される JSON Web トークンであり、1 時間有効です。 より長いライフタイムのリフレッシュ トークンも提供されます。 アクセス トークンの有効期限が切れると、Office クライアントは有効な更新トークンを使用して新しいアクセス トークンを取得します。 ユーザーの初期認証がまだ有効である場合、この交換は成功します。  <br/>  更新トークンは 90 日間有効で、継続して使用されていれば、取り消されるまで有効です。  <br/>  更新トークンは、次のような複数のイベントにより無効になる可能性があります。  <br/>  更新トークンが発行されてからユーザーのパスワードが変更された。  <br/>  管理者は、ユーザーがアクセスしようとするリソースへのアクセスを制限する、条件付きのアクセス ポリシーを適用できる。  <br/> |
|Android、iOS、Windows 10 用の SharePoint および OneDrive モバイル アプリ  <br/> |アクセス トークンの既定の有効期間は 1 時間です。 更新トークンの既定の最大非アクティブ期間は 90 日間です。  <br/> [トークンの詳細およびトークンの有効期間を構成する方法](/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> 更新トークンを無効にするには、ユーザーの Microsoft 365 パスワードを再設定します。  <br/> |
|Microsoft 365 サインインで Yammer を管理する  <br/> |ブラウザーの有効期間。 ユーザーがブラウザーを閉じて新しいブラウザーで Yammer にアクセスすると、Yammer は Microsoft 365 でユーザーを再認証します。 ユーザーが Cookie をキャッシュするサードパーティのブラウザを使用している場合、ブラウザを再度開いたときに再認証する必要がない場合があります。  <br/> > [!NOTE]> これは、Yammer 用の Microsoft 365 サインインを使用するネットワークでのみ有効です。           |