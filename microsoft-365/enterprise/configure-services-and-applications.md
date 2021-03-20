---
title: Microsoft 365 Enterprise サービスとアプリケーションを構成する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: deployment
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 7cec08a5-97fd-4761-b23b-ef3d66519e30
f1.keywords:
- NOCSH
description: SharePoint、Exchange、Skype for Business などの Microsoft 365 Enterprise サービスとアプリケーションを構成します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1aab85f049385a9569eb88f6feade6e6653da1e9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911140"
---
# <a name="configure-microsoft-365-enterprise-services-and-applications"></a>Microsoft 365 Enterprise サービスとアプリケーションを構成する

Microsoft [の基本的なセットアップ手順は](../admin/setup/setup.md) 、Microsoft 365 サービスとアプリケーションを使用しているすべてのユーザーを、可能な限り短時間で使用するのに役立ちます。 すべてのユーザーが使用を開始する前に構成された情報が優先される場合があります。 たとえば、メール ルーティング、ファイル ストレージ、または共有ポリシーを構成する場合。 
  
Microsoft 365 のセットアップに関するヘルプが必要な場合は **[、FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)** または [Microsoft 365 および 365 サービスのセットアップ ガイドOffice使用してください](setup-guides-for-microsoft-365.md)。
  
|**サービスおよびアプリケーション**|**リソース**|
|:-----|:-----|
|**Microsoft 365 スイート** |- [会社のブランド化を Microsoft 365 サインイン ページに追加する](https://support.office.com/article/Add-your-company-branding-to-Office-365-Sign-In-Page-a1229cdb-ce19-4da5-90c7-2b9b146aef0a) <br> - [カスタマイズしたヘルプ デスク情報を Microsoft 365 ヘルプ ウィンドウに追加する](https://support.office.com/article/Add-customized-help-desk-info-to-the-Office-365-help-pane-9dd9b104-68f7-4d49-9a30-82561c7d79a3) <br> - [Office 365 管理者の統合アプリおよび Azure AD](https://support.office.com/article/Integrated-Apps-and-Azure-AD-for-Office-365-administrators-cb2250e3-451e-416f-bf4e-363549652c2a)。  <br> - [Office 365 グループの概要](https://support.office.com/Article/Learn-more-about-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) <br> - [Microsoft 365 でモバイル デバイス管理をアクティブ化して使用する](https://support.office.microsoft.com/article/Manage-mobile-devices-in-Office-365-dd892318-bc44-4eb1-af00-9db5430be3cd) <br> - [Microsoft 365 接続の監視](monitor-connectivity.md) |
|**電子メール** <br> (Exchange Online) | [Exchange 展開アシスタントを使って Exchange ハイブリッド](https://technet.microsoft.com/exdeploy2013)の移行を開始する  <br> -[Exchange 移行アドバイザー](https://aka.ms/office365setup)を使用して、カスタマイズしたセットアップ ガイダンスを使う  <br> - [Exchange Online Protection をセットアップする](../security/office-365-security/set-up-your-eop-service.md) |
|**サイト** <br> (SharePoint Online) | -SharePoint Server [2013 のハイブリッド機能を構成する](/SharePoint/hybrid/hybrid)<br> - [サイト テンプレートを作成して使用](https://support.office.com/article/Create-and-use-site-templates-60371B0F-00E0-4C49-A844-34759EBDD989) し、SharePoint Online の外観をカスタマイズする <br> - [SharePoint Online 計画ガイド](https://support.office.com/article/SharePoint-Online-Planning-Guide-for-Office-365-for-business-d5089cdf-3fd2-4230-acbd-20ecda2f9bb8)または[SharePoint Online 展開アドバイザー](https://aka.ms/spoguidance)を使用してその他の機能の計画と構成をする <br> - ビデオ ポータル [を管理する](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da) |
|**IM および オンライン会議** <br> (Skype for Business Online) | - Lync Server [2013](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-2013-hybrid)または[Skype for Business 2015 のハイブリッド機能を構成](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)する<br> - [Skype for Business Online のセットアップ](https://support.office.com/article/Set-up-Skype-for-Business-Online-40296968-e779-4259-980b-c2de1c044c6e)を行い、通話ルーティング、電話会議、共有などの一般的な機能を構成する  <br> - [Skype for Business 展開アドバイザー](/MicrosoftTeams/faq-journey)を使用して、 カスタマイズしたセットアップ ガイダンスを使う |
| **ファイル ストレージおよび共有** <br> (OneDrive for Business と SharePoint Online) | - [Microsoft 365](https://support.office.com/article/7aa9cdc8-2245-4218-81ee-86fa7c35f1de#BKMK_WhatDif)ファイルストレージと共有のセットアップ : OneDrive for Business を使用してファイルを保存する必要がある場合と、ShharePoint Online チーム サイトを使用する必要がある場合について説明します。 <br> - [ファイルストレージと共有を設定](https://support.office.com/article/7aa9cdc8-2245-4218-81ee-86fa7c35f1de#BKMK_MoveDocsVideo)する : OneDrive for Business と SharePoint チーム サイトでファイルをアップロードする方法を確認する <br> - [ファイルストレージと共有を設定する](https://support.office.com/article/7aa9cdc8-2245-4218-81ee-86fa7c35f1de#BKMK_Store): OneDrive for Business とチーム サイトにファイルをアップロードするためのすべての手順を取得します。 ファイル共有のヒントを学ぶ <br> - [OneDrive for Business セットアップ ガイド](https://aka.ms/OD4Bguidance)を使用して、カスタマイズしたセットアップ ガイダンスを使う |
|**Microsoft 365 アプリケーション** | - Microsoft 365 管理者は[](/deployoffice)、Office展開ガイドを使用して、エンタープライズ展開またはアップグレード用の Microsoft 365 Apps の計画に関するヘルプを取得する必要があります。  <br> - [Power BI for Microsoft 365 管理センター](https://support.office.com/article/Power-BI-for-Office-365-Admin-Center-Help-5e391ecb-500c-47a3-bd0f-a6173b541044) <br> - [Office Microsoft 365 管理者向け Delve](https://support.office.com/article/Office-Delve-for-Office-365-admins-54f87a42-15a4-44b4-9df0-d36287d9531b) <br> - [Sway についてよく寄せられる質問](https://support.office.com/article/446380fa-25bf-47b2-996c-e12cb2f9d075) <br> - [Project Online の使用を開始する](https://support.office.com/article/Get-started-with-Project-Online-e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)。  <br> - [Microsoft Intune 展開アドバイザー](/mem/intune/) |
|**エンタープライズ ソーシャル** <br> (Yammer) | - [Microsoft 365 Yammerを使用する](https://support.office.com/article/Plan-for-Yammer-integration-with-Office-365-4086681f-6de1-4d39-aa72-752b2af1cbd7)  <br> - [Yammer Enterprise セットアップ ガイド](https://aka.ms/yammerdeploy)を使用して、カスタマイズしたセットアップ ガイダンスを使う |