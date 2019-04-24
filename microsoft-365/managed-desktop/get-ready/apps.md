---
title: Microsoft マネージドデスクトップのアプリの準備
description: ''
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: be28760fc3facdb21643943ace11deda378d437c
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289069"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップのアプリの準備

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
microsoft および microsoft の管理されたデスクトップのお客様は、microsoft マネージドデスクトップで使用されるアプリケーションに関して、同じように重要な責任を持っています。

## <a name="microsoft-responsibilities"></a>Microsoft の責任
**Office 365 アプリ**Microsoft は、特定の Office 365 アプリの展開、更新、およびサポートに対して完全なサービスを提供します。 すべてのユーザーは、ユーザーがすぐに生産性を向上させることができるように、デバイスの画像に含まれているアプリケーションの64ビットバージョンの Office 365 を実行するための基本セットを受信します。 Office 365 スイートのプロジェクトと Visio アプリケーションは個別にライセンスされています。  Microsoft マネージドデスクトップは、IT 管理者がライセンスを管理して、組織に適したアプリケーションを展開できるようにする展開グループを提供します。 microsoft は、microsoft マネージドデスクトップサポートチャネルを使用して、これらのアプリケーションのエンドユーザーをサポートします。

**基幹業務アプリ**Microsoft は、IT 管理者が、基幹業務 (LOB) アプリケーションを管理し、Intune 製品の一部としてエンドユーザーに展開するためのツールを提供しています。 Microsoft は、[基幹業務アプリケーション](#line-of-business-applications)で詳細なアプリケーション展開の問題をサポートします。 

**Intune を使用して展開**するintune は、microsoft**の**管理デスクトップオンボードにリンクされており、intune を使用して、調達アプリを展開できます。 また、microsoft Store からエンドユーザーに会社のポータルアプリケーションを展開することで、IT 管理者がエンドユーザーに対してセルフサービスを提供できるようにします。

**アプリ管理**Microsoft は、システムに影響を与えるため、モダンワークプレースに適さない制限付きアプリケーションを特定することができます。 このようなアプリケーションが検出されると、お客様に通知され、そのアプリケーションをテナントから削除する必要があります。 

制限されたアプリの動作とアプリの要件の詳細については、「 [Microsoft Managed Desktop app の要件](../service-description/mmd-app-requirements.md)」を参照してください。

## <a name="customer-responsibilities"></a>お客様の責任
Office 365 スイートは、microsoft の生産性向上のための中核であり、microsoft のすべての管理対象デスクトップユーザーの microsoft 365 ライセンスに含まれています。 microsoft が管理するデスクトップデバイスに対して office アプリケーションを展開、更新、サポートする一方で、お客様が責任を持ついくつかの分野があります。
- **ライセンスの割り当て**-お客様は、Office 365 のエンドユーザーに適切なライセンスを割り当てる必要があります。 
- **ユーザーをセキュリティグループに追加する**-プロジェクトまたは Visio を必要とするユーザーを持つ顧客の場合、IT 管理者は、それらのユーザーを適切な展開グループに追加する必要があります。 IT 管理者は、これらのユーザーの有効期限の管理も担当します。 
- **office 365 アドオンを展開**する-お客様は必要と思われる office 365 スイートにプラグインを展開する責任があります。 

基幹業務 (LOB) アプリは顧客ごとに一意であるため、お客様は Microsoft によって展開されていない組織内のすべてのアプリケーションを管理する責任があります。 これには以下が含まれます。
- 必要なアプリとそれらを必要とするアプリを決定する
- これらのユーザーにアプリを割り当てる
- アプリの割り当てを管理するための Azure Active Directory (AD) グループを作成して管理する 

お客様は LOB アプリを Intune にアップロードする必要があります。 その後、それらのアプリケーションをそれぞれのライフサイクルを通じて展開、更新、および使用停止し、ユーザー用のこれらのアプリのサポートを管理する責任があります。

## <a name="office-applications"></a>Office アプリケーション
microsoft 365 E5 ライセンスの一部として、Office 365 Standard Suite (64 ビット) は microsoft によって展開されています。 

詳細については、「 [Microsoft Managed Desktop technologies](../intro/technologies.md) 」を参照してください。 <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a>基幹業務アプリケーション
この表は、基幹業務 (LOB) アプリケーションのさまざまなフェーズにおける責任を要約しています。 

アプリケーション作業項目 |    顧客    | Microsoft
--- | --- | ---
**オンボードアプリ** |  |
対象ユーザーグループに必要なアプリケーションを特定する   | ![はい](images/checkmark.png)  |
アプリ展開用の Azure AD グループを作成および管理する | ![はい](images/checkmark.png) |   
**アプリのパッケージ化** |  |
Intune の展開基準を満たすようにアプリをパッケージ化する |  ![はい](images/checkmark.png) |  
アプリを Intune にアップロードする | ![はい](images/checkmark.png)     |
Microsoft マネージドデスクトップ環境でアプリをテストする |    ![はい](images/checkmark.png) |  
エンドユーザーとのアプリのテスト    | ![はい](images/checkmark.png) |    
**展開** | |
アプリケーションに対するユーザーの管理と割り当て  | ![はい](images/checkmark.png)  |
Intune 展開ツールがリモートクライアントにアプリケーションを提供する| |   ![はい](images/checkmark.png)
Intune を使用してアプリケーションの更新を識別して展開する | ![はい](images/checkmark.png)    |
Unistall が廃止されたときにアプリケーションを削除する    | ![はい](images/checkmark.png) |    
**管理** | |
ライセンスの調達と割り当て |   ![はい](images/checkmark.png)     |
基幹業務アプリのエンドユーザーサポートを提供する  | ![はい](images/checkmark.png) |
アプリの設定をリモートで管理する    | ![はい](images/checkmark.png) |

LOB アプリケーションの要件の詳細については、「 [Microsoft Managed Desktop application の要件](../service-description/mmd-app-requirements.md)」を参照してください。


## <a name="intune-application-deployment"></a>Intune アプリケーションの展開
アプリケーション管理は、Microsoft Managed Desktop Admin portal または Intune ポータルを使用して処理できます。 Intune のアプリ管理ポータルには、Windows、Android、iOS 用に展開されたアプリケーションが表示されます。 Microsoft Managed Desktop 管理ポータルでは、ビューが Windows 10 アプリケーションに制限されます。 どちらも Azure ポータルから利用できます。 
* [Intune アプリ管理の基本](https://docs.microsoft.com/intune/app-management)
* [Intune にアプリを追加する](https://docs.microsoft.com/intune/app-management)
   * [基幹業務アプリを追加する](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Win32 アプリを Intune に追加する](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [web アプリケーションを追加する](https://docs.microsoft.com/intune/web-app)
* [アプリを展開する](https://docs.microsoft.com/intune/apps-deploy)
   * [Windows 10 にアプリを展開する](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* 会社のポータル
   * [会社のポータルを展開する](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [ポータルサイトアプリを構成する](https://docs.microsoft.com/intune/company-portal-app)
