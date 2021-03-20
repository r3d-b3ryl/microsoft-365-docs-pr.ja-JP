---
title: 'Microsoft 365 クライアント アプリのサポート: 条件付きアクセス'
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
description: この記事では、Microsoft 365 の条件付きアクセスをサポートするプラットフォーム、クライアント、および PowerShell モジュールについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7b0b65ea25091aad01fd8741f9925f2b545e9c4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904968"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a>Microsoft 365 クライアント アプリのサポート: 条件付きアクセス

最新の職場では、ユーザーはどこからでもさまざまなデバイスやアプリを使用して組織のリソースにアクセスできます。 その結果、リソースにアクセスできるユーザーに焦点を当てるだけで十分ではありません。 組織は、アクセス制御インフラストラクチャでリソースにアクセスする方法と場所もサポートする必要があります。

Azure Active Directory デバイス、場所、および多要素認証ベースの条件付きアクセスを使用すると、この新しい要件を満たします。 条件付きアクセスは Azure Active Directory の機能であり、環境内のアプリへのアクセスに対する制御を適用できます。これは、すべて特定の条件に基づいて、中央の場所から管理されます。

[Azure Active Directory 条件付きアクセスの詳細については、次を参照してください](/azure/active-directory/conditional-access/)。

## <a name="supported-clients--platforms"></a>サポートされているクライアント&プラットフォーム

次のクライアントとプラットフォームの最新バージョンでは、条件付きアクセスがサポートされています。 Microsoft 365 でのプラットフォームサポートの詳細については [、「Microsoft 365](/microsoft-365/microsoft-365-and-office-resources)のシステム要件」を参照してください。
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a>サポートされている PowerShell モジュール

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online の PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
