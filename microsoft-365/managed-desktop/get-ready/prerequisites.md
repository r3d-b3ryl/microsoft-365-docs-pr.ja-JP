---
title: Microsoft マネージド デスクトップの前提条件
description: ''
keywords: 管理されたデスクトップの Microsoft、Microsoft 365 サービス マニュアル
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.openlocfilehash: 303765d6804071b3a3de18ee412304566cbbe089
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869511"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップの前提条件

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

Microsoft 管理されたデスクトップでの成功は、お客様のインフラストラクチャの要件をよく知られている、文書化されて合意から始まります。このセクションでは、これらの前提条件について説明します。 

FastTrack の Microsoft は、これらの要件を満たすし、サービスとして最新のワークプ レースに参加するための準備を支援する使用できます。詳細については、[マイクロソフトの FastTrack](https://fasttrack.microsoft.com/about)を参照してください。 

項目 | 前提条件の詳細
--- | ---
ライセンス | 365 E5 の Microsoft ライセンスまたは同等のライセンスが必要です。<br><br>このライセンスには、Office 365 の E5、Windows 10 エンタープライズ E5 とエンタープライズ モビリティ + E5 のセキュリティ (EMS) が含まれています。詳細については、[マイクロソフトの 365 のライセンス](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)を参照してください。
接続 |  内部の組織のネットワークから多数の Microsoft のサービス エンドポイントに接続が必要管理されたデスクトップの Microsoft のすべてのデバイスを含みます。<br>Windows の更新プログラム<br>ビジネス向けのマイクロソフト ストア<br>-Azure Active Directory<br>Windows エラー報告<br>-オンライン クラッシュ ダンプ解析<br>接続されているユーザーの経験および遠隔測定<br>-10 の Windows のアプリケーションを OneDrive<br><br>IP のための完全な一覧に必要な[プロキシ](../get-ready/network.md)構成 Url が見つかりません。 
Azure Active Directory |    Azure Active Directory (AD の Azure) では、ソースのすべてのユーザー アカウントの権限をする必要がありますか、または、Azure の AD 接続では、バージョン 1.1.654.0 を使用して、オンプレミスの Active Directory からユーザー アカウントを同期する必要があります以降。詳細については、 [Azure AD 接続](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)を参照してください。
認証 |    Azure AD がユーザー アカウントの権限の元でない場合は、Azure AD 接続] で次のいずれかを構成する必要があります。<br>のパスワード ハッシュの同期 (推奨)<br>パススルー認証<br>連合に ADFS を使用しました。<br><br>Azure AD 接続パスワードの書き戻しを使用して認証オプションを設定する必要がも。詳細については、[パスワードの書き戻し](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)を参照してください。<br><br>Azure AD の認証オプションの詳細については、 [Azure AD 接続ユーザーのサインインのオプション](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)を参照してください。
Office 365 |    次のサービスをクラウドに移行することを強くお勧めします。<br>-電子メール - クラウド ベースのメールボックス、Exchange オンラインへの移行または、Exchange オンライン ハイブリッド Exchange 2013 以降で、設置型で構成されます。<br>-ファイルとフォルダーの – に SharePoint オンライン/Office 365 に移行します。<br>-ビジネス – Skype に移行する Skype のビジネス オンライン。
デバイスの管理 | Intune のマイクロソフトのクラウド専用 MDM ソリューション (ハイブリッドではない) は必須では世界中の任意の場所からアクセスできる web コンソールを使用して Microsoft 管理デスクトップ デバイスを管理する IT 管理者を作成することができます。Microsoft Intune は、必要な MDM ソリューションです。<br><br>詳細については、 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)を参照してください。 
データのバックアップとリカバリ | Microsoft 管理されたデスクトップでは、ファイルを保護するためのビジネスの OneDrive を同期する必要があります。ビジネスの OneDrive に同期されていないすべてのファイルは、管理されたデスクトップのマイクロソフトでは保証されず、デバイスの交換、またはデバイスのリセットを必要とするサポート コール中に失われる可能性があります。Microsoft 管理されたデスクトップでは、マップされたネットワーク ドライブはサポートされていません。  

[Microsoft 管理デスクトップ登録の前提条件を満たすための方法を説明します。](../get-ready/index.md)

Microsoft 管理されたデスクトップを開始する準備ができたらは、マイクロソフトのアカウント マネージャーに問い合わせてください。 
