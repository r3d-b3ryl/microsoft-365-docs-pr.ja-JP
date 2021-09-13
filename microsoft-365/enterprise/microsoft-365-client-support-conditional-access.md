---
title: 'Microsoft 365クライアント アプリのサポート: 条件付きアクセス'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: この記事では、条件付きアプリケーションをサポートするプラットフォーム、クライアント、および PowerShell モジュールAccess for Microsoft 365。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 763380429b8643c5dd01971117fccb040a9a0210
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215953"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a>Microsoft 365クライアント アプリのサポート: 条件付きアクセス

最新の職場では、ユーザーはどこからでもさまざまなデバイスやアプリを使用して組織のリソースにアクセスできます。 その結果、リソースにアクセスできるユーザーに焦点を当てるだけで十分ではありません。 組織は、アクセス制御インフラストラクチャでリソースにアクセスする方法と場所もサポートする必要があります。

デバイスAzure Active Directory、多要素認証ベースの条件付きアクセスを使用すると、この新しい要件を満たします。 条件付きアクセスは、Azure Active Directoryの機能であり、環境内のアプリへのアクセスに対して、特定の条件に基づいて制御を適用し、中央の場所から管理できます。

条件付きアクセスの[詳細Azure Active Directoryを参照してください](/azure/active-directory/conditional-access/)。

## <a name="supported-clients--platforms"></a>サポートされているクライアント&プラットフォーム

次のクライアントとプラットフォームの最新バージョンでは、条件付きアクセスがサポートされています。 プラットフォームサポートの詳細については、「Microsoft 365のシステム要件」[を参照Microsoft 365。](/microsoft-365/microsoft-365-and-office-resources)
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a>サポートされている PowerShell モジュール

- [Azure Active DirectoryPowerShell](/powershell/azure/active-directory/overview)
- [Exchange Online の PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePointオンライン PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
