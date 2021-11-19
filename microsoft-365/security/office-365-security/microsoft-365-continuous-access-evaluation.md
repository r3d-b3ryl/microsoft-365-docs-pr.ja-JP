---
title: エンタープライズ向け Microsoft 365のMicrosoft 365評価
description: Microsoft 365および Azure ADの条件付きアクセス評価がアクティブ なユーザー セッションを積極的に終了し、ほぼリアルタイムでテナント ポリシーの変更を適用する方法について説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-overview
ms.technology: mdo
ms.openlocfilehash: ba810e129d7f2634e3708ecc32b7e20a1db8f170
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110957"
---
# <a name="continuous-access-evaluation-for-microsoft-365"></a>ユーザーの継続的なアクセスMicrosoft 365

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)

認証に OAuth 2.0 を使用する最新のクラウド サービスは、従来、ユーザー アカウントのアクセスを取り消すアクセス トークンの有効期限に依存しています。 実際には、管理者がユーザー アカウントのアクセスを取り消した場合でも、ユーザーはアクセス トークンの有効期限が切れるまでアクセス権を持ち続け、既定では Microsoft 365 の場合は、最初の失効イベントが発生した後、最大 1 時間後に使用されます。

Microsoft 365 および Azure Active Directory (Azure AD) の条件付きアクセス評価は、アクティブなユーザー セッションを積極的に終了し、アクセス トークンの有効期限に依存するのではなく、ほぼリアルタイムでテナント ポリシーの変更を適用します。 Azure ADは、ユーザー アカウントまたはテナントがユーザー アカウントの認証状態の再評価を必要とする方法で変更された場合に、継続的アクセス評価が有効な Microsoft 365 サービス (SharePoint、Teams、Exchange など) に通知します。

Outlook などの継続的なアクセス評価が有効なクライアントが既存のアクセス トークンを使用して Exchange にアクセスしようとすると、トークンはサービスによって拒否され、新しい Azure AD 認証を求めるメッセージが表示されます。 その結果、ユーザー アカウントとポリシーの変更がほぼリアルタイムで適用されます。

その他の利点を次に示します。

- 組織外で有効なアクセス トークンをコピーしてエクスポートする悪意のあるインサイダーの場合、継続的なアクセス評価では、IP アドレスの場所ポリシーを使用してこのトークンAzure AD使用を防止します。 継続的なアクセス評価により、Azure AD はポリシーをサポートされている Microsoft 365 サービスに同期するため、アクセス トークンがポリシーの IP アドレス範囲外からサービスにアクセスしようとすると、サービスはトークンを拒否します。

- 継続的なアクセス評価により、トークンの更新を少なくする必要が生じ、復元性が向上します。 サポート サービスは再認証の要求に関する予防的な通知を受け取るので、Azure ADは、たとえば 1 時間を超えて、より長い期間のトークンを発行できます。 有効期限が長いトークンでは、クライアントはトークンの更新を要求する必要がAzure AD、ユーザー エクスペリエンスの回復性が向上します。

継続的なアクセス評価によってユーザー アクセス制御のセキュリティが向上する状況の例を次に示します。

- ユーザー アカウントのパスワードが侵害されたので、管理者は既存のすべてのセッションを無効にし、パスワードを管理者からリセットMicrosoft 365 管理センター。 ほぼリアルタイムで、すべての既存のユーザー セッションとサービスMicrosoft 365無効になります。

- Word でドキュメントを操作しているユーザーは、タブレットを管理者定義の承認済み IP アドレス範囲に含めないパブリック コーヒーショップに持ち込む。 コーヒーショップでは、ユーザーのドキュメントへのアクセスが直ちにブロックされます。

このMicrosoft 365、継続的なアクセス評価は現在、次の項目でサポートされています。

- Exchange、SharePoint、およびTeamsサービス。
- Outlookブラウザー Teams、Office、および OneDrive Win32、iOS、Android、および Mac クライアントの場合。

Microsoft は、継続的なアクセス評価Microsoft 365サポートするために、追加のサービスとクライアントに取り組み続け中です。

継続的なアクセス評価は、すべてのバージョンのサーバーとOffice 365に含Microsoft 365。 条件付きアクセス ポリシーを構成するには、Azure AD Premium P1すべてのバージョンに含まれるMicrosoft 365必要があります。

> [!NOTE]
> 継続的 [アクセス評価の](/azure/active-directory/conditional-access/concept-continuous-access-evaluation#limitations) 制限事項については、この記事を参照してください。

## <a name="scenarios-supported-by-microsoft-365"></a>ユーザーがサポートするシナリオMicrosoft 365

継続的アクセス評価では、次の 2 種類のイベントがサポートされます。

- 重要なイベントは、ユーザーがアクセスを失う必要があるイベントです。
- 条件付きアクセス ポリシーの評価は、ユーザーが管理者定義のポリシーに基づいてリソースへのアクセスを失う必要がある場合に発生します。

重要なイベントは次のとおりです。

- ユーザー アカウントが無効になっている
- パスワードが変更される
- ユーザー セッションが取り消される
- ユーザーに対して多要素認証が有効になっている
- Id Protection からのアクセスの評価に基づいてアカウント[リスクAzure AD増加](/azure/active-directory/identity-protection/overview-identity-protection)

条件付きアクセス ポリシーの評価は、ユーザー アカウントが信頼できるネットワークから接続しなくなったときに発生します。

現在、次Microsoft 365サービスは、ユーザーからのイベントをリッスンして継続的なアクセス評価をAzure AD。

<br>

****

|適用の種類|Exchange|SharePoint|Teams|
|---|---|---|---|
|**重要なイベント:**||||
|ユーザーの失効|サポート|サポート|サポート|
|ユーザーのリスク|サポート|サポート対象外|サポート対象外|
|**条件付きアクセス ポリシーの評価:**||||
|IP アドレスの場所ポリシー|サポート|サポート\*|サポート|
|

\*SharePoint Office Web ブラウザー アクセスは、厳密モードを有効にすることで、インスタント IP ポリシーの適用をサポートします。 厳密なモードを使用しない場合、アクセス トークンの有効期間は 1 時間です。

条件付きアクセス ポリシーを設定する方法の詳細については、この記事を [参照してください](/azure/active-directory/conditional-access/overview)。

## <a name="microsoft-365-clients-supporting-continuous-access-evaluation"></a>Microsoft 365評価をサポートするクライアント

Microsoft 365 の継続的アクセス評価が有効なクライアントは、キャッシュされたユーザー トークンが継続的アクセス評価対応 Microsoft 365 サービスによって拒否された場合に、ユーザー セッションを Azure AD にリダイレクトして再認証する要求チャレンジをサポートします。

次のクライアントは、Web、Win32、iOS、Android、および Mac での継続的なアクセス評価をサポートしています。

- Outlook
- Teams
- 事業所\*
- SharePoint
- OneDrive

\*クレームチャレンジは、web のOfficeサポートされていません。

継続的なアクセス評価をサポートしないクライアントの場合、アクセス トークンの有効期間は既定Microsoft 365 1 時間のままです。

## <a name="see-also"></a>関連項目

- [継続的アクセス評価](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)
- [条件付きアクセスのドキュメント](/azure/active-directory/conditional-access/overview)
- [Azure AD Id Protection のドキュメント](/azure/active-directory/identity-protection/overview-identity-protection)
