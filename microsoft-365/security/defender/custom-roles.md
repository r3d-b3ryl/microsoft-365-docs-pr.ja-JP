---
title: 役割ベースのアクセス制御のカスタム ロール
description: カスタム ロールを管理する方法については、Microsoft 365 Defenderしてください。
keywords: アクセス、アクセス許可、Microsoft 365 Defender、M365、セキュリティ、MCAS、Cloud App Security、Microsoft Defender for Endpoint、スコープ、スコープ、RBAC、役割ベースのアクセス、カスタム の役割ベースのアクセス、役割ベースの認証、MDO の RBAC、役割、役割グループ、アクセス許可の継承、詳細なアクセス許可
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 699d8c1d8ea7ac6928c96b6c98226ab82e0725fb
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214613"
---
# <a name="custom-roles-in-role-based-access-control-for-microsoft-365-defender"></a>ユーザーの役割ベースのアクセス制御のカスタム ロールMicrosoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**適用対象:**

- Microsoft 365 Defender
 
ユーザーにアクセスするために使用できる役割には、次の 2 種類Microsoft 365 Defender。
- **グローバル Azure Active Directory (AD) の役割**
- **カスタムの役割**

グローバル Microsoft 365 Defender (AAD) でグローバル ロールを使用して、Azure Active Directoryアクセス[を管理できます。](m365d-permissions.md)

特定の製品データへのアクセスを柔軟に制御する必要がある場合は、Microsoft 365 Defender各セキュリティ ポータルを使用してカスタム ロールを作成してアクセスを管理することもできます。  

たとえば、Microsoft Defender for Endpoint を介して作成されたカスタム ロールを使用すると、関連する製品データ (ポータル内のエンドポイント データを含む) にMicrosoft 365 Defenderされます。 同様に、Microsoft Defender for Office 365 を使用して作成されたカスタム ロールを使用すると、関連する製品データ (& ポータル内の電子メール コラボレーション データなど) にMicrosoft 365 Defenderできます。

既存のカスタム ロールを持つユーザーは、追加の構成を必要とMicrosoft 365 Defender既存のワークロードのアクセス許可に従って、Microsoft 365 Defender ポータルのデータにアクセスできます。

## <a name="create-and-manage-custom-roles"></a>カスタム ロールの作成と管理
カスタム ロールとアクセス許可は、次の各セキュリティ ポータルを介して作成および個別に管理できます。 

- Microsoft Defender for Endpoint – [エンドポイント用 Microsoft Defender の役割を編集する](../defender-endpoint/user-roles.md)
- Microsoft Defender for Office 365 – セキュリティ コンプライアンス センター&[アクセス許可](../office-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide)
- Microsoft Cloud App Security –[管理者アクセスを管理する](/cloud-app-security/manage-admins)

個々のポータルを介して作成された各カスタム ロールにより、関連する製品ポータルのデータにアクセスできます。 たとえば、Microsoft Defender for Endpoint を介して作成されたカスタム ロールは、Defender for Endpoint データへのアクセスのみを許可します。

> [!TIP]
> アクセス許可と役割は、ナビゲーション ウィンドウから [アクセス許可] Microsoft 365 Defenderロールを選択して、&ポータルからアクセスすることもできます。 MCAS Microsoft Cloud App Securityアクセスは MCAS ポータルを通じて管理され、Microsoft Defender for Identity へのアクセスも制御します。  詳細[については、「Microsoft Cloud App Security](/cloud-app-security/manage-admins)

> [!NOTE]
> ユーザー設定で作成Microsoft Cloud App Security、Id データの Microsoft Defender にもアクセスできます。 ユーザー グループ管理者、または App/instance 管理者Microsoft Cloud App Securityロールを持つユーザーは、Microsoft Cloud App SecurityポータルをMicrosoft 365 Defenderできません。

## <a name="manage-permissions-and-roles-in-the-microsoft-365-defender-portal"></a>ポータルでアクセス許可と役割をMicrosoft 365 Defenderする
アクセス許可と役割は、次のポータルでもMicrosoft 365 Defenderできます。

1. [ポータル] の Microsoft 365 Defenderにサインイン security.microsoft.com。
2. ナビゲーション ウィンドウで、**[アクセス許可と役割]** を選択します。
3. [アクセス許可 **] ヘッダーで** 、[役割] を **選択します**。

> [!NOTE]
> これは、Defender for Office 365エンドポイントにのみ適用されます。 他のワークロードへのアクセスは、関連するポータルで行う必要があります。


## <a name="required-roles-and-permissions"></a>必要な役割と権限
次の表に、各ワークロードの各統合エクスペリエンスにアクセスするために必要な役割とアクセス許可の概要を示します。 以下の表で定義されている役割は、個々のポータルのカスタム ロールを参照し、同様に名前が付けられた場合でも、Azure AD のグローバル ロールには接続されません。

> [!NOTE]
> インシデント管理には、インシデントの一部であるすべての製品の管理権限が必要です。
 
| **次のいずれかの役割が必要ですMicrosoft 365 Defender**  | **Defender for Endpoint では、次のいずれかの役割が必要です**  | **Defender では、次の役割の 1 つが必要Office 365** | **次のいずれかの役割が必要ですCloud App Security** | 
|---------|---------|---------|---------|
| 調査データの表示: <ul><li>[アラート] ページ</li> <li>アラート キュー</li> <li>インシデント</li>  <li>インシデント キュー</li> <li>アクション センター</li></ul>| データの表示 - セキュリティ操作 | <ul><li>[表示のみ] アラートの管理 </li> <li>組織の構成</li><li>監査ログ</li> <li>表示のみ可能な監査ログ</li> <li>セキュリティ閲覧者</li> <li>セキュリティ管理者</li><li>表示専用の受信者</li></ul>  | <ul><li>グローバル管理者</li> <li>セキュリティ管理者</li> <li>コンプライアンス管理者</li> <li>セキュリティ オペレーター</li> <li>セキュリティ閲覧者</li> <li>グローバル閲覧者</li></ul> |
| ハンティング データの表示 | データの表示 - セキュリティ操作 | <ul><li>セキュリティ閲覧者</li> <li>セキュリティ管理者</li> <li>表示専用の受信者</li> | <ul><li>グローバル管理者</li> <li>セキュリティ管理者</li> <li>コンプライアンス管理者</li> <li>セキュリティ オペレーター</li> <li>セキュリティ閲覧者</li> <li>グローバル閲覧者</li></ul> |
| アラートとインシデントの管理 | アラートの調査 | <ul><li>アラートの管理</li> <li>セキュリティ管理者</li> | <ul><li>グローバル管理者</li> <li>セキュリティ管理者</li> <li>コンプライアンス管理者</li> <li>セキュリティ オペレーター</li> <li>セキュリティ閲覧者</li></ul> |
| アクション センターの修復 | アクティブな修復アクション – セキュリティ操作 | 検索と削除 | |
| カスタム検出の設定 | セキュリティ設定の管理 |<ul><li>アラートの管理</li> <li>セキュリティ管理者</li></ul> | <ul><li>グローバル管理者</li> <li>セキュリティ管理者</li> <li>コンプライアンス管理者</li> <li>セキュリティ オペレーター</li> <li>セキュリティ閲覧者</li> <li>グローバル閲覧者</li></ul> |
| 脅威の分析 | アラートとインシデント のデータ: <ul><li>データの表示 - セキュリティ操作</li></ul>TVM の軽減策:<ul><li>データの表示 - 脅威と脆弱性の管理</li></ul> | アラートとインシデント のデータ:<ul> <li>[表示のみ] アラートの管理</li> <li>アラートの管理</li> <li>組織の構成</li><li>監査ログ</li> <li>表示のみ可能な監査ログ</li><li>セキュリティ閲覧者</li> <li>セキュリティ管理者</li><li>表示専用の受信者</li> </ul> 電子メールの試行を防止します。 <ul><li>セキュリティ閲覧者</li> <li>セキュリティ管理者</li><li>表示専用の受信者</li> | MCAS または MDI ユーザーには使用できません |

たとえば、Microsoft Defender for Endpoint のハンティング データを表示するには、データ セキュリティ操作のアクセス許可を表示する必要があります。  

同様に、Microsoft Defender のハンティング データを表示Office 365、ユーザーは次のいずれかの役割を必要とします。  

- データ セキュリティ操作の表示
- セキュリティ閲覧者
- セキュリティ管理者
- 表示専用の受信者

## <a name="related-topics"></a>関連項目
- [Microsoft 365 Defender へのアクセスを管理する](m365d-permissions.md)
- [MCAS の管理者アクセスを管理する](/cloud-app-security/manage-admins)
