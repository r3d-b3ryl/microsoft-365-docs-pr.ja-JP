---
title: Microsoft 管理デスクトップ テクノロジ
description: このトピックには、テクノロジと Microsoft の管理されたデスクトップで使用されているアプリケーションが一覧表示されます。
keywords: 管理されたデスクトップの Microsoft、Microsoft 365 サービス マニュアル
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 4b26ec88e1f4ca95fee6f7c4c927fc06cab32135
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869204"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft 管理デスクトップ テクノロジ

このトピックには、テクノロジと Microsoft の管理されたデスクトップで使用されているアプリケーションが一覧表示されます。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 E5 ライセンス (またはそれと同等) は、管理されたデスクトップの Microsoft のサービスに必要です。このライセンスおよび管理されたデスクトップのマイクロソフトがマイクロソフトの管理されたデスクトップ デバイスと各コンポーネントを使用する方法に含まれるすべてのコンポーネントを次に示します。 各領域の特定の役割と責任はマイクロソフトの管理されたデスクトップのトピックで詳しく説明します。 

Microsoft 365 E5 は、3 つのコンポーネントで構成されています: Office 365 の E5、10 企業の Windows と E5、エンタープライズ モビリティ + セキュリティ E5 します。  

## <a name="office-365-e5"></a>Office 365 E5
 |
 --- | ---
Office 365 の標準的なスイート (64 ビット) * | デバイスとアプリケーションの標準的な Office スイートが出荷されます。 Word、Excel、PowerPoint、Outlook、Publisher、アクセス、ビジネス、OneNote の Skype です。<br><br>64 ビットの実行をクリックして Microsoft Project および Microsoft Visio の完全バージョンを (C2R) は、Office 365 の標準的なスイートでは含まれません。 ただし、これらのアプリケーションのインストールが標準の Office スイートのインストールに依存するため、Microsoft の管理されたデスクトップが作成既定 Intune 展開し、これらのアプリケーションを展開するお客様が使用するセキュリティ グループエンド ・ ユーザーのライセンスを取得します。  
ストア アプリ |    マイクロソフト支配下に置いた、マイクロソフトのチーム、BI デスクトップの電源 (はない) に付属していないデバイスです。これらのアプリケーションは、Microsoft ストアからダウンロードできます。
Win32 アプリケーション |    電源双 Pro、Azure 情報保護クライアント、および Microsoft の計画は、デバイスに付属していないと、お客様が配置のパッケージ化することができます。 
Web アプリケーション |  Yammer、Delve、Office オンラインのフロー、StaffHub、PowerApps は、デバイスに付属していません。ユーザーは、web ブラウザーを使用してこれらのアプリケーションのバージョンにアクセスできます。
ビジネス オンライン クラウド PBX の Skype | この機能は、Office 365 の E5 を使用します。Microsoft 管理されたデスクトップはこのサービスのすべての側面を構成していません。

## <a name="windows-10-enterprise-e5"></a>10 の Windows エンタープライズ E5

 |
 --- | ---
資格情報の保護 |  Microsoft 管理されたデスクトップ、ガイダンスを用意し、この機能をクラウドの側面を管理
デバイス保護 (Windows Defender のアプリケーションのコントロール) | Microsoft 管理されたデスクトップでは、ポリシーを作成します。顧客では、署名を管理します。
AppLocker の管理 |  Microsoft 管理されたデスクトップでは、ポリシーを作成します。顧客では、署名を管理します。
アプリケーションの仮想化 (APP-V) |    Microsoft 管理デスクトップがこの種類の展開をサポートしていません Intune でサポートされていないようです。
ユーザー エクスペリエンスの仮想化 (UE V) | 管理 Microsoft 管理デスクトップ デバイスとこれは、使用できません。
管理のユーザー エクスペリエンス  | これはデバイスの管理 Microsoft 管理されたデスクトップでは使用されません。MDM は、デバイス管理のソリューションとして使用します。
Windows Defender Advanced Threat Protection |   デバイスのセキュリティ ポリシーを管理する Microsoft 管理されたデスクトップで使用されます。 

## <a name="enterprise-mobility--security"></a>Enterprise Mobility + Security 

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory プレミアム P2 |    MDM のデバイスを管理するエンタープライズ モビリティとセキュリティの E3 と AADP のすべての側面を使用することがあります。
Microsoft Cloud App Security |  これは、管理されたデスクトップの Microsoft のサービスを顧客が使用できるオプション機能です。
Azure の情報保護の P2  |これは、管理されたデスクトップの Microsoft のサービスを顧客が使用できるオプション機能です。
