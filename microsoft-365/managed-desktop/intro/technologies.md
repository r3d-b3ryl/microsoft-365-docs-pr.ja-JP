---
title: Microsoft マネージドデスクトップテクノロジ
description: このトピックでは、Microsoft マネージドデスクトップで使用されるテクノロジとアプリの一覧を示します。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9c0e6481d0dc80e7cf03de2b748935c2f59f132a
ms.sourcegitcommit: e54ec86310a18101f4688890cd5a9fc16bbe6f55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2019
ms.locfileid: "35257820"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft マネージドデスクトップテクノロジ

このトピックでは、Microsoft マネージドデスクトップで使用されるテクノロジとアプリの一覧を示します。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise ライセンスは、Microsoft が管理するすべてのデスクトップユーザーに必要です。 サービスのライセンス要件の詳細については、「 [Microsoft マネージドデスクトップの前提条件](../get-ready/prerequisites.md)」を参照してください。

必要なエンタープライズライセンスに含まれるすべてのコンポーネントと、サービスが Microsoft マネージドデスクトップデバイスで各コンポーネントを使用する方法を以下に示します。 各領域の特定の役割と責任は、「Microsoft Managed Desktop」のトピック全体で詳細に説明します。 

## <a name="office-365-e3"></a>Office 365 E3
 |
 --- | ---
Office 365 Standard Suite (64 ビット) * | 標準の Office スイートアプリケーションは、デバイス (Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote) に同梱されています。<br><br>C2R (64 ビット) をクリックして実行する () フルバージョンの Microsoft Project と Microsoft Visio は Office 365 Standard スイートに含まれていません。  ただし、これらのアプリケーションのインストールは標準の Office スイートのインストールに依存しているため、Microsoft マネージドデスクトップでは、これらのアプリケーションを展開するために使用する既定の Intune 展開およびセキュリティグループが作成されています。ライセンスされたエンドユーザー。  
ストアアプリ |    Microsoft Sway、Power BI Desktop はデバイスと共には同梱されていません。 これらのアプリは Microsoft ストアからダウンロードできます。
Win32 アプリケーション |    Power BI Pro、Azure Information Protection クライアント、および Microsoft Planner はデバイスに同梱されておらず、お客様が展開用にパッケージ化することもできます。 
Web アプリケーション |  Yammer、Office Online、Delve、Flow、StaffHub、PowerApps は、デバイスに同梱されていません。 ユーザーは、ブラウザーを使用して、これらのアプリケーションの web バージョンにアクセスできます。
Skype for Business Online クラウド PBX | この機能は、Office 365 で利用できます。 Microsoft マネージドデスクトップでは、このサービスの一部は構成されません。

## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise E5

 |
 --- | ---
Credential Guard |  Microsoft は、この機能のガイダンスを提供し、クラウドの側面を管理します。
Application Virtualization (App-v) |    Microsoft マネージドデスクトップでは、この種類の展開は Intune ではサポートされていないため、サポートされていません。
User Experience Virtualization (UE-V) | これは、Microsoft マネージドデスクトップで管理されているデバイスでは使用されません。
管理対象ユーザーの環境  | これは、Microsoft マネージドデスクトップで管理されているデバイスでは使用されません。 MDM は、デバイス管理のソリューションとして使用されます。
Windows Defender Advanced Threat Protection |   これは、デバイスのセキュリティポリシーを管理するために Microsoft マネージドデスクトップによって使用されます。 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Enterprise Mobility + Security E3 および AADP のすべての側面を使用して MDM デバイスを管理できます。
Microsoft Cloud App Security |  これは、お客様が Microsoft Managed Desktop service で使用できるオプションの機能です。
Azure Information Protection P2  |これは、お客様が Microsoft Managed Desktop service で使用できるオプションの機能です。
