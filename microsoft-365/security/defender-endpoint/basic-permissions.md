---
title: 基本的なアクセス許可を使用してMicrosoft Defender セキュリティ センターにアクセスする
description: 基本的なアクセス許可を使用してMicrosoft Defender for Endpoint ポータルにアクセスする方法について説明します。
keywords: ユーザー ロールの割り当て、読み取りおよび書き込みアクセスの割り当て、読み取り専用アクセスの割り当て、ユーザー、ユーザー ロール、ロール
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
ms.openlocfilehash: 27c480a0d4c95e79619e10f8fa42efb2c268b18c
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2021
ms.locfileid: "61171715"
---
# <a name="use-basic-permissions-to-access-the-portal"></a>基本的なアクセス許可を使用してポータルにアクセスする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- Azure Active Directory
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-basicaccess-abovefoldlink)

基本的なアクセス許可管理を使用するには、以下の手順を参照してください。

次のいずれかのソリューションを使用できます。

- Azure PowerShell
- Azure portal

アクセス許可をきめ細かく制御するには、 [ロールベースのアクセス制御に切り替えます](rbac.md)。

## <a name="assign-user-access-using-azure-powershell"></a>Azure PowerShellを使用してユーザー アクセスを割り当てる

次のいずれかのレベルのアクセス許可を持つユーザーを割り当てることができます。

- フル アクセス (読み取りと書き込み)
- 読み取り専用アクセス

### <a name="before-you-begin"></a>開始する前に

- Azure PowerShell をインストールします。 詳細については、「[Azure PowerShellをインストールして構成する方法](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)」を参照してください。

  > [!NOTE]
  > 管理者特権のコマンド ラインで PowerShell コマンドレットを実行する必要があります。

- Azure Active DirectoryにConnectします。 詳細については、「[Connect-MsolService](/powershell/module/msonline/connect-msolservice)」を参照してください。

  - **フル アクセス**: フル アクセスのユーザーは、ログイン、すべてのシステム情報の表示、アラートの解決、詳細な分析のためのファイルの送信、オンボード パッケージのダウンロードを行うことができます。 フル アクセス権を割り当てるには、ユーザーを "セキュリティ管理者" または "グローバル管理者" AAD組み込みロールに追加する必要があります。
  - **読み取り専用アクセス**: 読み取り専用アクセス権を持つユーザーは、ログイン、すべてのアラート、関連情報の表示を行うことができます。

    アラートの状態を変更したり、詳細な分析のためにファイルを送信したり、状態を変更する操作を実行したりすることはできません。

    読み取り専用アクセス権を割り当てるには、組み込みロールAzure AD "Security Reader" にユーザーを追加する必要があります。

セキュリティ ロールを割り当てるには、次の手順に従います。

- **読み取りおよび書き込み** アクセス権の場合は、次のコマンドを使用してユーザーをセキュリティ管理者ロールに割り当てます。

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```

- **読み取り専用** アクセスの場合は、次のコマンドを使用してユーザーをセキュリティ リーダー ロールに割り当てます。

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

詳細については、「[Azure Active Directoryを使用してグループ メンバーを追加または削除する](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)」を参照してください。

## <a name="assign-user-access-using-the-azure-portal"></a>Azure portalを使用してユーザー アクセスを割り当てる

詳細については、「Azure Active Directoryを[持つユーザーに管理者ロールと管理者以外のロールを割り当てる](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)」を参照してください。

## <a name="related-topic"></a>関連トピック

- [RBAC を使用してポータル アクセスを管理する](rbac.md)
