---
title: 基本的なアクセス許可を使用してアクセスMicrosoft Defender セキュリティ センター
description: 基本的なアクセス許可を使用して Microsoft Defender for Endpoint ポータルにアクセスする方法について説明します。
keywords: ユーザー ロールの割り当て、読み取りおよび書き込みアクセスの割り当て、読み取り専用アクセスの割り当て、ユーザー、ユーザー の役割、役割
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 05e9eadb9047fd4a2c8a4d01ecefc3ec2f73f9db
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207991"
---
# <a name="use-basic-permissions-to-access-the-portal"></a>基本的なアクセス許可を使用してポータルにアクセスする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- Azure Active Directory
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-basicaccess-abovefoldlink)

基本的なアクセス許可管理を使用するには、以下の手順を参照してください。

次のいずれかのソリューションを使用できます。

- Azure PowerShell
- Azure portal

アクセス許可を詳細に制御するには [、役割ベースのアクセス制御に切り替えます](rbac.md)。

## <a name="assign-user-access-using-azure-powershell"></a>ユーザー アクセスを割り当てるには、Azure PowerShell

次のいずれかのレベルのアクセス許可を持つユーザーを割り当てできます。

- フル アクセス (読み取りおよび書き込み)
- 読み取り専用アクセス

### <a name="before-you-begin"></a>はじめに

- Azure PowerShell をインストールします。 詳細については、「How to install and configure Azure PowerShell」[を参照してください](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)。

  > [!NOTE]
  > 管理者特権のコマンド ラインで PowerShell コマンドレットを実行する必要があります。

- ConnectにAzure Active Directory。 詳細については[、「Connect-MsolService」を参照してください](/powershell/module/msonline/connect-msolservice)。

  - **フル アクセス**: フル アクセスのユーザーは、ログイン、すべてのシステム情報の表示、アラートの解決、詳細な分析のためのファイルの送信、オンボーディング パッケージのダウンロードを行うことができます。 フル アクセス権を割り当てるには、ユーザーを "セキュリティ管理者" または "グローバル管理者" AAD 組み込みロールに追加する必要があります。
  - **読み取り専用アクセス**: 読み取り専用アクセス権を持つユーザーは、ログイン、すべての通知、および関連情報を表示できます。

    アラートの状態を変更したり、詳細な分析のためにファイルを送信したり、状態の変更操作を実行したりできない。

    読み取り専用アクセス権を割り当てるには、ユーザーを "Security Reader" Azure AD組み込みロールに追加する必要があります。

セキュリティ ロールを割り当てるには、次の手順を使用します。

- 読 **み取りおよび書き込** みアクセスの場合は、次のコマンドを使用してセキュリティ管理者の役割にユーザーを割り当てる必要があります。

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```

- 読 **み取り専用アクセスの** 場合は、次のコマンドを使用してユーザーをセキュリティ リーダー ロールに割り当てる必要があります。

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

詳細については、「グループ メンバーを使用してグループ メンバーを追加または削除する」[を参照Azure Active Directory。](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

## <a name="assign-user-access-using-the-azure-portal"></a>Azure portal を使用してユーザー アクセスを割り当てる

詳細については、「管理者と管理者以外の役割[を](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)ユーザーに割り当てる」を参照Azure Active Directory。

## <a name="related-topic"></a>関連トピック

- [RBAC を使用してポータル アクセスを管理する](rbac.md)
