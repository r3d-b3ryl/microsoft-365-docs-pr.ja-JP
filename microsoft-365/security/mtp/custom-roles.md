---
title: 役割ベースのアクセス制御のカスタム ロール
description: Microsoft 365 セキュリティ センターでカスタム ロールを管理する方法について説明します。
keywords: access、 permissions, MTP, Microsoft Threat Protection, M365, security, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, scope, scoping, RBAC, role-based access, custom role-based access, role-based auth, RBAC in MDO, role, rolegroups, permissions inheritance, fine-grained permissions
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 35ac4e26406fe6fde1385008b527dc4865e0392b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928930"
---
# <a name="custom-roles-in-role-based-access-control-for-microsoft-365-defender"></a>Microsoft 365 Defender の役割ベースのアクセス制御のカスタム ロール

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**適用対象:**

- Microsoft 365 Defender
 
Microsoft 365 Defender へのアクセスに使用できる役割には、次の 2 種類があります。
- **グローバル Azure Active Directory (AD) ロール**
- **カスタム ロール**

Microsoft 365 Defender へのアクセスは[、Azure Active Directory (AAD)](mtp-permissions.md)のグローバル ロールを使用してまとめて管理できます。

特定の製品データへのアクセスを柔軟に制御する必要がある場合、Microsoft 365 Defender アクセスは、それぞれのセキュリティ ポータルを介してカスタム ロールを作成して管理することもできます。  

たとえば、Microsoft Defender for Endpoint を介して作成されたカスタム ロールを使用すると、Microsoft 365 セキュリティ センター内のエンドポイント データを含む関連する製品データにアクセスできます。 同様に、microsoft Defender for Office 365 で作成されたカスタム ロールでは、Microsoft 365 セキュリティ センター内のメール & コラボレーション データなど、関連する製品データにアクセスできます。

既存のカスタム ロールを持つユーザーは、既存のワークロードのアクセス許可に従って Microsoft 365 セキュリティ センターのデータにアクセスできます。追加の構成は不要です。

## <a name="create-and-manage-custom-roles"></a>カスタム ロールの作成と管理
カスタム ロールとアクセス許可は、次の各セキュリティ ポータルを介して作成および個別に管理できます。 

- Microsoft Defender for Endpoint – [エンドポイント用 Microsoft Defender の役割を編集する](/windows/security/threat-protection/microsoft-defender-atp/user-roles)
- Microsoft Defender for Office 365 – セキュリティ コンプライアンス センター& [アクセス許可](../office-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide)
- Microsoft Cloud App Security – [管理者アクセスを管理する](/cloud-app-security/manage-admins)

個々のポータルを介して作成された各カスタム ロールにより、関連する製品ポータルのデータにアクセスできます。 たとえば、Microsoft Defender for Endpoint を介して作成されたカスタム ロールは、Defender for Endpoint データへのアクセスのみを許可します。

> [!TIP]
> アクセス許可と役割は、ナビゲーション ウィンドウから [アクセス許可] と [役割の&選択して、Microsoft 365 セキュリティ センターからアクセスすることもできます。 Microsoft Cloud App Security (MCAS) へのアクセスは MCAS ポータルを通じて管理され、Microsoft Defender for Identity へのアクセスも制御します。  [「Microsoft Cloud App Security」を参照してください。](/cloud-app-security/manage-admins)

> [!NOTE]
> Microsoft Cloud App Security で作成されたカスタム ロールは、Id データ用の Microsoft Defender にもアクセスできます。 ユーザー グループ管理者またはアプリ/インスタンス管理者の Microsoft Cloud App Security ロールを持つユーザーは、Microsoft 365 セキュリティ センターを介して Microsoft Cloud App Security データにアクセスできない。

## <a name="manage-permissions-and-roles-in-the-microsoft-365-security-center"></a>Microsoft 365 セキュリティ センターでアクセス許可と役割を管理する
アクセス許可と役割は、Microsoft 365 セキュリティ センターでも管理できます。

1. Microsoft 365 セキュリティ センター (microsoft 365 セキュリティ センター) にサインイン security.microsoft.com。
2. ナビゲーション ウィンドウで、[アクセス許可] **を選択&します**。
3. [アクセス許可 **] ヘッダーで** 、[役割] を **選択します**。

> [!NOTE]
> これは、Defender for Office 365 および Defender for Endpoint にのみ適用されます。 他のワークロードへのアクセスは、関連するポータルで行う必要があります。


## <a name="required-roles-and-permissions"></a>必要な役割と権限
次の表に、各ワークロードの各統合エクスペリエンスにアクセスするために必要な役割とアクセス許可の概要を示します。 以下の表で定義されている役割は、個々のポータルのカスタム ロールを参照し、同様に名前が付けられた場合でも、Azure AD のグローバル ロールには接続されません。

> [!NOTE]
> インシデント管理には、インシデントの一部であるすべての製品に対する管理アクセス許可が必要です。
 
| **Microsoft 365 Defender では、次のいずれかの役割が必要です**  | **Defender for Endpoint では、次のいずれかの役割が必要です**  | **365 の Defender に必要な役割は、次Officeです。** | **Cloud App Security では、次のいずれかの役割が必要です** | 
|---------|---------|---------|---------|
| 調査データの表示: <ul><li>[アラート] ページ</li> <li>アラート キュー</li> <li>インシデント</li>  <li>インシデント キュー</li> <li>アクション センター</li></ul>| データの表示 - セキュリティ操作 | <ul><li>[表示のみ] アラートの管理 </li> <li>組織の構成</li><li>監査ログ</li> <li>表示のみ可能な監査ログ</li> <li>セキュリティ閲覧者</li> <li>セキュリティ管理者</li><li>表示専用の受信者</li></ul>  | <ul><li>グローバル管理者</li> <li>セキュリティ管理者</li> <li>コンプライアンス管理者</li> <li>セキュリティ オペレーター</li> <li>セキュリティ閲覧者</li> <li>グローバルリーダー</li></ul> |
| ハンティング データの表示 | データの表示 - セキュリティ操作 | <ul><li>セキュリティ閲覧者</li> <li>セキュリティ管理者</li> <li>表示専用の受信者</li> | <ul><li>グローバル管理者</li> <li>セキュリティ管理者</li> <li>コンプライアンス管理者</li> <li>セキュリティ オペレーター</li> <li>セキュリティ閲覧者</li> <li>グローバルリーダー</li></ul> |
| アラートとインシデントの管理 | アラートの調査 | <ul><li>アラートの管理</li> <li>セキュリティ管理者</li> | <ul><li>グローバル管理者</li> <li>セキュリティ管理者</li> <li>コンプライアンス管理者</li> <li>セキュリティ オペレーター</li> <li>セキュリティ閲覧者</li></ul> |
| アクション センターの修復 | アクティブな修復アクション – セキュリティ操作 | 検索と削除 | |
| カスタム検出の設定 | セキュリティ設定の管理 |<ul><li>アラートの管理</li> <li>セキュリティ管理者</li></ul> | <ul><li>グローバル管理者</li> <li>セキュリティ管理者</li> <li>コンプライアンス管理者</li> <li>セキュリティ オペレーター</li> <li>セキュリティ閲覧者</li> <li>グローバルリーダー</li></ul> |
| Threat Analytics | アラートとインシデント のデータ: <ul><li>データの表示 - セキュリティ操作</li></ul>TVM の軽減策:<ul><li>データの表示 - 脅威と脆弱性の管理</li></ul> | アラートとインシデント のデータ:<ul> <li>[表示のみ] アラートの管理</li> <li>アラートの管理</li> <li>組織の構成</li><li>監査ログ</li> <li>表示のみ可能な監査ログ</li><li>セキュリティ閲覧者</li> <li>セキュリティ管理者</li><li>表示専用の受信者</li> </ul> 電子メールの試行を防止します。 <ul><li>セキュリティ閲覧者</li> <li>セキュリティ管理者</li><li>表示専用の受信者</li> | MCAS または MDI ユーザーには使用できません |

たとえば、Microsoft Defender for Endpoint のハンティング データを表示するには、データ セキュリティ操作のアクセス許可を表示する必要があります。  

同様に、Microsoft Defender for Office 365 のハンティング データを表示するには、次のいずれかの役割が必要です。  

- データ セキュリティ操作の表示
- セキュリティ閲覧者
- セキュリティ管理者
- 表示専用の受信者

## <a name="related-topics"></a>関連項目
- [Microsoft 365 Defender へのアクセスを管理する](mtp-permissions.md)
- [MCAS の管理者アクセスを管理する](/cloud-app-security/manage-admins)