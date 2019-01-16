---
title: デスクトップを管理する Microsoft のアプリケーションを準備します。
description: ''
keywords: 管理されたデスクトップの Microsoft、Microsoft 365 サービス マニュアル
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: b46e3de4a4cfe2140574ab9fc589e3a738bd2e17
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869202"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>デスクトップを管理する Microsoft のアプリケーションを準備します。

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
マイクロソフトおよびマイクロソフトの管理されたデスクトップの顧客は、Microsoft 管理されたデスクトップで使用するアプリケーションに重要なまだ別の責任である均等にします。

## <a name="microsoft-responsibilities"></a>Microsoft の責任
**Office 365 アプリケーション**マイクロソフトでは、展開、更新、および特定の Office 365 アプリケーションのサポートの完全なサービスが提供されます。ユーザーが生産性を迅速にするために、デバイスのイメージに含まれるアプリケーションの 64 ビット バージョンを実行する] をクリックを Office 365 の基本セットは、すべてのユーザーが表示されます。Office 365 製品ファミリの内のプロジェクトおよび Visio のアプリケーションは個別にライセンスされています。 Microsoft 管理されたデスクトップ展開グループがライセンスを管理し、各組織に適切にこれらのアプリケーションを展開する IT 管理者が提供されます。マイクロソフトは、Microsoft 管理されたデスクトップのサポート チャネルを通じてこれらのアプリケーションのエンド ・ ユーザーをサポートします。

**基幹業務アプリケーション**マイクロソフトでは、IT 管理者の管理および Intune 製品の一部として、基幹業務 (LOB) アプリケーションをエンドユーザーに展開するためのツールを提供します。マイクロソフトをサポートする[基幹業務アプリケーション](#line-of-business-applications)を「アプリケーションの展開に関する問題 

**Intune と展開**Intune は、Intune によって展開される調達されたアプリケーションを許可する管理されたデスクトップのマイクロソフトの契約時の中に**ビジネスのためのマイクロソフト ストア**にリンクされます。IT 管理者は、エンド ・ ユーザーのセルフ サービス エクスペリエンスを提供できるように Microsoft はエンド ・ ユーザーにも企業ポータルの web ベースのバージョンを展開します。

**アプリケーションの管理**マイクロソフトでは、システムに対する影響があるため、現代の職場に適したない制限されたアプリケーションを識別可能性があります。指定は、このようなアプリケーションと Microsoft を顧客に通知がそのアプリケーションはテナントから削除する必要があります。 

制限されたアプリケーションの動作とアプリケーションの要件の詳細については、[マイクロソフトの管理されたデスクトップ アプリケーションの要件](../service-description/mmd-app-requirements.md)を参照してください。

## <a name="customer-responsibilities"></a>お客様の責任範囲
Office 365 製品ファミリは、マイクロソフトの生産性ソリューションの中核し、Microsoft 管理されたデスクトップのすべてのユーザーの Microsoft 365 ライセンスに含まれています。マイクロソフトの展開、更新、およびデスクトップ管理されているデバイスを Microsoft Office アプリケーションをサポートしているときに、お客様の責任の一部の領域はまだあります.
- **ライセンスを割り当てる**には、お客様の Office 365 のエンド ・ ユーザーへの適切なライセンスの割り当てを担当します。 
- **セキュリティ グループにユーザーの追加**のプロジェクトまたは Visio を必要としているユーザーとお客様の IT 管理者する必要がありますそれらのユーザー グループに追加、適切な展開。IT 管理者も、それらのユーザーの寿命の最後の管理を担当します。 
- **Office 365 に追加のアドオンの導入**のお客様は、任意のプラグインを必要と判断した場合は、Office 365 製品ファミリに展開を担当します。 

基幹業務 (LOB) アプリケーションが顧客ごとに一意であるために、お客様はマイクロソフトが展開していない組織内のすべてのアプリケーションを管理する責任者です。これが含まれています。
- どのアプリが必要し、それらが必要なユーザーを決定します。
- それらのユーザーにアプリケーションを割り当てる
- 作成し、アプリケーションの割り当てを管理するための Azure Active Directory (AD) のグループの管理 

お客様は、Intune に LOB アプリケーションをアップロードする必要があります。展開を更新して、それぞれのライフ サイクル上でそれらのアプリケーションの使用を停止として、これらのアプリケーションのユーザーのサポートを管理する責任は。

## <a name="office-applications"></a>Office アプリケーション
365 E5 のマイクロソフト ライセンスの一部として、microsoft Office 365 の標準的なスイート (64 ビット) が配置されます。 

詳細については、[管理されたデスクトップの Microsoft テクノロジ](../intro/technologies.md)を参照してください。<!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a>基幹業務アプリケーション
このテーブルでは、基幹業務 (LOB) アプリケーションのさまざまなフェーズの間で責任の範囲をまとめたものです。 

アプリケーション作業項目 |    顧客    | Microsoft
--- | --- | ---
**契約時のアプリケーション** |  |
対象となるユーザー グループに必要なアプリケーションを特定します。   | ![はい](images/checkmark.png)  |
作成および管理アプリケーションの展開の Azure AD グループ | ![はい](images/checkmark.png) |   
**アプリケーションのパッケージ化** |  |
Intune 展開の標準に準拠してアプリケーションをパッケージ |  ![はい](images/checkmark.png) |  
Intune にアプリケーションをアップロードします。 | ![はい](images/checkmark.png)     |
Microsoft 管理されたデスクトップ環境でアプリケーションをテストします。 |    ![はい](images/checkmark.png) |  
エンド ・ ユーザーによるアプリケーションのテスト    | ![はい](images/checkmark.png) |    
**展開** | |
管理し、ユーザーをアプリケーションに割り当てる  | ![はい](images/checkmark.png)  |
Intune 展開ツールは、リモート クライアントにアプリケーションを提供します。| |   ![はい](images/checkmark.png)
識別し、Intune によってアプリケーションの更新プログラムの展開 | ![はい](images/checkmark.png)    |
それらが使用されなくなったときにアプリケーションをアンインストールし、削除    | ![はい](images/checkmark.png) |    
**管理** | |
調達し、ライセンスを割り当てる |   ![はい](images/checkmark.png)     |
基幹業務アプリケーションのエンド ユーザー サポートを提供します。  | ![はい](images/checkmark.png) |
アプリケーション設定を管理するリモート    | ![はい](images/checkmark.png) |

LOB アプリケーションの要件については、[マイクロソフトの管理されたデスクトップ アプリケーションの要件](../service-description/mmd-app-requirements.md)を参照してください。


## <a name="intune-application-deployment"></a>Intune アプリケーションの配置
Microsoft デスクトップ管理の管理ポータル、または Intune ポータルを通じて、アプリケーションの管理を処理できます。Intune のアプリケーションの管理ポータルは、Windows、Android、iOS の配置されたアプリケーションを示しています。マイクロソフト デスクトップ管理の管理ポータルでは、10 の Windows アプリケーションに表示を制限します。両方は、Azure ポータルを使用します。 
* [Intune アプリケーション管理の基礎](https://docs.microsoft.com/intune/app-management)
* [Intune にアプリケーションを追加します。](https://docs.microsoft.com/intune/app-management)
   * [基幹業務アプリケーションを追加します。](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Intune に Win32 アプリケーションを追加します。](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Web アプリケーションを追加します。](https://docs.microsoft.com/intune/web-app)
* [アプリケーションを展開します。](https://docs.microsoft.com/intune/apps-deploy)
   * [10 [Windows へのアプリケーションを展開します。](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* 企業ポータル
   * [企業ポータルを展開します。](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [会社のポータル アプリケーションを構成します。](https://docs.microsoft.com/intune/company-portal-app)
