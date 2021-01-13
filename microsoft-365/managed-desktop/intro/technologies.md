---
title: Microsoft マネージド デスクトップのテクノロジ
description: この記事では、Microsoft マネージド デスクトップで使用されるテクノロジとアプリの一覧を示します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: cb368939e87ddbbfc8f5386c6fc5d6bff110a7ec
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840903"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft マネージド デスクトップのテクノロジ

この記事では、Microsoft マネージド デスクトップで使用されるテクノロジとアプリの一覧を示します。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise ライセンスは、すべての Microsoft マネージド デスクトップ ユーザーに必要です。 サービスのライセンス要件の詳細については、「Microsoft マネージド デスクトップの前提条件」 [を参照してください](../get-ready/prerequisites.md)。

この記事では、必要なエンタープライズ ライセンスに含まれるコンポーネントの概要と、サービスが Microsoft マネージド デスクトップ デバイスで各コンポーネントを使用する方法について説明します。 各領域の特定の役割と責任については、Microsoft マネージド デスクトップのドキュメント全体で詳しく説明します。 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 または E5
 |
 --- | ---
Microsoft 365 Apps for enterprise (64 ビット) | これらのOffice、Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote のデバイスに同梱されます。<br><br>64 ビット版の Microsoft Project および Microsoft Visio は含まれていません。 ただし、これらのアプリケーションのインストールは Microsoft 365 Apps for enterprise インストールに依存します。このため、Microsoft マネージド デスクトップでは、ライセンスを取得したユーザーにこれらのアプリケーションを展開するために使用できる既定の Microsoft Intune 展開とセキュリティ グループが作成されています。 詳細については、「Microsoft マネージ デスクトップ デバイスへの [Microsoft Project または Microsoft Visio のインストール」を参照してください](../get-started/project-visio.md)。
OneDrive |Azure Active Directory シングル サインオンは、ユーザーが初めて OneDrive にサインインするときに有効になります。<br><br>"Desktop"、"Document"、および "Pictures" フォルダーの既知のフォルダー リダイレクトが含まれます。有効にし、Microsoft マネージド デスクトップによって構成されます。
ストア アプリ |    Microsoft Sway と Power BI はデバイスに同梱されません。 これらのアプリは、Microsoft Store からダウンロードできます。
Win32 アプリケーション |    Teams はデバイスに同梱されませんが、Microsoft マネージド デスクトップ デバイス用に Microsoft によってパッケージ化および提供されます。 Azure Information Protection クライアントはデバイスに同梱されませんが、展開用にパッケージ化することができます。
Web アプリケーション |  Yammer、Office Delve、Flow、StaffHub、PowerApps、Planner はデバイスに同梱されません。 ユーザーはブラウザーを使用してこれらのアプリケーションの Web バージョンにアクセスできます。


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 または E3 と Microsoft Defender for Endpoint

 |
 --- | ---
Application Virtualization (App-V) |    お客様は、Intune Win32 アプリ管理クライアントを使用して App-V パッケージを展開できます。
Microsoft Defender for Endpoint |    Microsoft マネージド デスクトップは、この製品を使用してデバイスのセキュリティを監視します。 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Enterprise Mobility + Security E3 と Azure Active Directory Premium P2 のすべての機能を使用して、MDM デバイスを管理できます。
Microsoft Cloud App Security |  このオプション機能は、Microsoft マネージド デスクトップで使用できます。
Azure Information Protection P2  | このオプション機能は、Microsoft マネージド デスクトップで使用できます。
