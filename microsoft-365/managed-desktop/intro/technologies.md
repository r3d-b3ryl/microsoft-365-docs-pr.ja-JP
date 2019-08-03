---
title: Microsoft マネージドデスクトップテクノロジ
description: このトピックでは、Microsoft マネージドデスクトップで使用されるテクノロジとアプリの一覧を示します。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9f3094b1a1272b0c200271b8d5703fe7173683a6
ms.sourcegitcommit: 6b5370cded5d8259c9ed561eed324227f74c410b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2019
ms.locfileid: "36171737"
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
Office 365 standard suite (64 ビット) | 標準の Office スイートアプリケーションは、デバイス (Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote) に同梱されています。<br><br>C2R (Microsoft Project の完全バージョン) および Microsoft Visio が Office 365 に含まれていない場合は、64ビット版をクリックして実行します。 ただし、これらのアプリケーションのインストールは標準の Office スイートのインストールに依存しているため、Microsoft マネージドデスクトップでは、これらのアプリケーションを展開するために使用できる既定の Microsoft Intune 展開およびセキュリティグループが作成されています。ライセンスされたエンドユーザー。 詳細については、「microsoft [Project または Microsoft Visio を Microsoft マネージドデスクトップデバイスにインストール](../get-started/project-visio.md)する」を参照してください。  
ストアアプリ |    Microsoft Sway と Power BI は、デバイスに同梱されていません。 これらのアプリは Microsoft ストアからダウンロードできます。
Win32 アプリケーション |    Teams はデバイスに同梱されていませんが、microsoft マネージドデスクトップデバイス用にパッケージ化され、Microsoft によって提供されています。 Azure Information Protection クライアントはデバイスに同梱されていませんが、展開用にパッケージ化することができます。 
Web アプリケーション |  Yammer、browser 内の Office、Delve、Flow、StaffHub、PowerApps、および Planner は、デバイスに同梱されていません。 ユーザーは、ブラウザーを使用して、これらのアプリケーションの web バージョンにアクセスできます。


## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise E5

 |
 --- | ---
Application Virtualization (App-v) |    Microsoft マネージドデスクトップでは、Microsoft Intune でサポートされていないため、この種類の展開はサポートされていません。
Microsoft Defender Advanced Threat Protection |  Microsoft マネージドデスクトップは、これを使用してデバイスのセキュリティを監視します。 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Enterprise Mobility + Security E3 および Azure Active Directory Premium P2 のすべての機能を使用して、MDM デバイスを管理できます。
Microsoft Cloud App Security |  このオプション機能は、Microsoft マネージドデスクトップで使用できます。
Azure Information Protection P2  | このオプション機能は、Microsoft マネージドデスクトップで使用できます。
