---
title: Microsoft 365の継続的なアクセス評価 - エンタープライズ向けのMicrosoft 365
description: Microsoft 365とAzure ADの条件付きアクセスの評価によって、アクティブなユーザー セッションを事前に終了し、テナント ポリシーの変更をほぼリアルタイムで強制する方法について説明します。
ms.author: dansimp
author: dansimp
manager: dansimp
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 22927fbf85d9dab424c8b546b7e837bf035d8a2f
ms.sourcegitcommit: 9c8eca862a2f0fdca7a66c641e382e37fcaefa10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2022
ms.locfileid: "63775348"
---
# <a name="continuous-access-evaluation-for-microsoft-365"></a>Microsoft 365の継続的アクセス評価

認証に OAuth 2.0 を使用する最新のクラウド サービスは、従来、アクセス トークンの有効期限に依存してユーザー アカウントのアクセスを取り消しています。 実際には、これは、管理者がユーザー アカウントのアクセスを取り消した場合でも、アクセス トークンの有効期限が切れるまで、ユーザーは引き続きアクセス権を持ちます。既定では、Microsoft 365では、最初の失効イベントが発生してから最大 1 時間です。

Microsoft 365とAzure Active Directory (Azure AD) の条件付きアクセス評価では、アクセス トークンの有効期限に依存する代わりに、アクティブなユーザー セッションを事前に終了し、テナント ポリシーの変更をほぼリアルタイムで強制します。 Azure ADは、ユーザー アカウントまたはテナントがユーザー アカウントの認証状態の再評価を必要とする方法で変更されたときに、継続的アクセス評価が有効なMicrosoft 365 サービス (SharePoint、Teams、Exchangeなど) に通知します。

Outlookなどの継続的アクセス評価が有効なクライアントが既存のアクセス トークンを使用してExchangeにアクセスしようとすると、トークンはサービスによって拒否され、新しいAzure AD認証が求められます。 その結果、ユーザー アカウントとポリシーの変更がほぼリアルタイムで適用されます。

その他の利点を次に示します。

- 組織の外部で有効なアクセス トークンをコピーしてエクスポートする悪意のあるインサイダーの場合、継続的なアクセス評価により、Azure AD IP アドレスの場所ポリシーを通じてこのトークンの使用が防止されます。 継続的アクセス評価では、Azure ADはポリシーをサポートされているMicrosoft 365 サービスに同期するため、アクセス トークンがポリシー内の IP アドレス範囲外からサービスにアクセスしようとすると、サービスはトークンを拒否します。

- 継続的なアクセス評価では、トークンの更新が少なくて済み、回復性が向上します。 サポート サービスは再認証の要求に関するプロアクティブな通知を受け取るため、Azure ADは有効期間の長いトークン (たとえば、1 時間以上) を発行できます。 有効期間が長いトークンでは、クライアントは頻繁にAzure ADからトークンの更新を要求する必要がないため、ユーザー エクスペリエンスの回復性が向上します。

継続的なアクセス評価によってユーザー アクセス制御のセキュリティが向上する状況の例を次に示します。

- ユーザー アカウントのパスワードが侵害されたため、管理者は既存のすべてのセッションを無効にし、Microsoft 365 管理センターからパスワードをリセットします。 ほぼリアルタイムで、Microsoft 365 サービスを使用するすべての既存のユーザー セッションが無効になります。

- Word でドキュメントを操作しているユーザーは、管理者が定義した承認済みの IP アドレス範囲にないパブリック コーヒー ショップにタブレットを移動します。 コーヒー ショップでは、ドキュメントへのユーザーのアクセスはすぐにブロックされます。

Microsoft 365では、継続的アクセス評価は現在、次の方法でサポートされています。

- Exchange、SharePoint、およびTeams サービス。
- Web ブラウザーと Win32、iOS、Android、Mac クライアントのOutlook、Teams、Office、およびOneDrive。

Microsoft は、継続的なアクセス評価をサポートするために、追加のMicrosoft 365 サービスとクライアントに取り組んでいます。

継続的アクセス評価は、Office 365とMicrosoft 365のすべてのバージョンに含まれます。 条件付きアクセス ポリシーを構成するには、すべてのMicrosoft 365 バージョンに含まれるAzure AD Premium P1が必要です。

> [!NOTE]
> 継続的アクセス評価の制限事項については、 [この記事](/azure/active-directory/conditional-access/concept-continuous-access-evaluation#limitations) を参照してください。

## <a name="scenarios-supported-by-microsoft-365"></a>Microsoft 365でサポートされるシナリオ

継続的アクセス評価では、次の 2 種類のイベントがサポートされます。

- 重要なイベントは、ユーザーがアクセスを失う必要があるイベントです。
- 条件付きアクセス ポリシーの評価は、ユーザーが管理者が定義したポリシーに基づいてリソースへのアクセスを失う必要がある場合に発生します。

重要なイベントは次のとおりです。

- ユーザー アカウントが無効になっている
- パスワードが変更されました
- ユーザー セッションが取り消される
- ユーザーに対して多要素認証が有効になっている
- アカウント リスクは、[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection) からのアクセスの評価に基づいて増加しました

条件付きアクセス ポリシーの評価は、ユーザー アカウントが信頼されたネットワークから接続されなくなったときに発生します。

現在、次のMicrosoft 365 サービスは、Azure ADからのイベントをリッスンすることで継続的なアクセス評価をサポートしています。

|適用の種類|Exchange|SharePoint|Teams|
|---|---|---|---|
|**重要なイベント:**||||
|ユーザー失効|サポート|サポート|サポート|
|ユーザーのリスク|サポート|非サポート|サポート対象外|
|**条件付きアクセス ポリシーの評価:**||||
|IP アドレスの場所ポリシー|サポート|サポート\*|サポート|

\*SharePoint Office Web ブラウザー アクセスでは、厳格なモードを有効にすることで、インスタント IP ポリシーの適用がサポートされます。 strict モードを使用しない場合、アクセス トークンの有効期間は 1 時間です。

条件付きアクセス ポリシーを設定する方法の詳細については、 [この記事](/azure/active-directory/conditional-access/overview)を参照してください。

## <a name="microsoft-365-clients-supporting-continuous-access-evaluation"></a>継続的なアクセス評価をサポートするクライアントをMicrosoft 365する

Microsoft 365の継続的アクセス評価が有効なクライアントは、要求チャレンジをサポートします。これは、キャッシュされたユーザー トークンが継続的アクセス評価が有効なMicrosoft 365 サービスによって拒否された場合に、再認証のためにユーザー セッションをAzure ADにリダイレクトすることです。

次のクライアントは、Web、Win32、iOS、Android、Mac での継続的なアクセス評価をサポートしています。

- Outlook
- Teams
- Office\*
- SharePoint
- OneDrive

\*要求チャレンジは、web のOfficeではサポートされていません。

継続的なアクセス評価をサポートしていないクライアントの場合、Microsoft 365へのアクセス トークンの有効期間は既定で 1 時間のままです。

## <a name="see-also"></a>関連項目

- [継続的アクセス評価](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)
- [条件付きアクセスに関するドキュメント](/azure/active-directory/conditional-access/overview)
- [Azure AD Identity Protection のドキュメント](/azure/active-directory/identity-protection/overview-identity-protection)
