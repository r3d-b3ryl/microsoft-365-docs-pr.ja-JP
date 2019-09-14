---
title: Microsoft マネージドデスクトップテクノロジ
description: このトピックでは、Microsoft マネージドデスクトップで使用されるテクノロジとアプリの一覧を示します。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 57c0be2e8aff09024f84c58bb895aab98324964d
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982538"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft マネージドデスクトップテクノロジ

このトピックでは、Microsoft マネージドデスクトップで使用されるテクノロジとアプリの一覧を示します。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise ライセンスは、Microsoft が管理するすべてのデスクトップユーザーに必要です。 サービスのライセンス要件の詳細については、「 [Microsoft マネージドデスクトップの前提条件](../get-ready/prerequisites.md)」を参照してください。

このトピックでは、必要なエンタープライズライセンスに含まれるコンポーネントの概要と、サービスが Microsoft マネージドデスクトップデバイスで各コンポーネントを使用する方法について説明します。 各分野の特定の役割と責任は、Microsoft マネージドデスクトップドキュメント全体で詳細に説明されています。 

## <a name="office-365-e3"></a>Office 365 E3
 |
 --- | ---
Office 365 ProPlus (64 ビット) | これらの Office アプリケーションは、Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote などのデバイスと共に出荷されます。<br><br>64ビット版の Microsoft Project と Microsoft Visio は含まれていません。 ただし、これらのアプリケーションのインストールは Office 365 ProPlus のインストールに依存しているため、Microsoft Managed Desktop では既定の Microsoft Intune 展開およびセキュリティグループが作成されており、これらのアプリケーションをライセンスに展開することができます。エンドユーザー。 詳細については、「microsoft [Project または Microsoft Visio を Microsoft マネージドデスクトップデバイスにインストール](../get-started/project-visio.md)する」を参照してください。
OneDrive for Business | Azure Active Directory シングルサインオン <br><br>「デスクトップ」、「ドキュメント」、「画像」フォルダーの既知のフォルダーのリダイレクトが含まれています。Microsoft マネージドデスクトップで有効化および構成されている。 
ストアアプリ |    Microsoft Sway と Power BI は、デバイスに同梱されていません。 これらのアプリは Microsoft ストアからダウンロードできます。
Win32 アプリケーション |    Teams はデバイスに同梱されていませんが、microsoft マネージドデスクトップデバイス用にパッケージ化され、Microsoft によって提供されています。 Azure Information Protection クライアントはデバイスに同梱されていませんが、展開用にパッケージ化することができます。 
Web アプリケーション |  Yammer、browser 内の Office、Delve、Flow、StaffHub、PowerApps、および Planner は、デバイスに同梱されていません。 ユーザーは、ブラウザーを使用して、これらのアプリケーションの web バージョンにアクセスできます。


## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise E5

 |
 --- | ---
Application Virtualization (App-v) |    ユーザーは、Intune Win32 app management クライアントを使用して App-v パッケージを展開できます。
Microsoft Defender Advanced Threat Protection |  Microsoft マネージドデスクトップは、これを使用してデバイスのセキュリティを監視します。 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Enterprise Mobility + Security E3 および Azure Active Directory Premium P2 のすべての機能を使用して、MDM デバイスを管理できます。
Microsoft Cloud App Security |  このオプション機能は、Microsoft マネージドデスクトップで使用できます。
Azure Information Protection P2  | このオプション機能は、Microsoft マネージドデスクトップで使用できます。
