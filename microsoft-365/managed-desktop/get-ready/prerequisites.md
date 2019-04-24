---
title: Microsoft マネージドデスクトップの前提条件
description: ''
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8d9c008af9531bc5b829d248665dc5b58ac6034b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277388"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップの前提条件

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

Microsoft マネージドデスクトップでの成功は、お客様のインフラストラクチャに関する既知の、ドキュメント化された要件、合意された要件を基に開始します。 このセクションでは、これらの infastructure の要件について概説します。 

microsoft fasttrack を使用すると、お客様がこれらの要件を満たし、microsoft の管理されたデスクトップに参加するための準備に役立てることができます。 詳細については、「 [Microsoft fasttrack](https://fasttrack.microsoft.com/about)」を参照してください。 

項目 | 前提条件の詳細
--- | ---
ライセンス | 各 MMD ユーザーには、次のいずれかのライセンスオプションが割り当てられている必要があります。<br>-Microsoft 365 E5<br>-Microsoft 365 E3、Enterprise Mobility + Security E5 および Windows 10 Enterprise E5<br>-Office 365 E3、Enterprise Mobility + Security E5 および Windows 10 Enterprise E5<br><br>既存のエンタープライズアグリーメントのお客様は、Azure AD テナントで Windows 10 Enterprise サブスクリプションのライセンス認証を有効にするために、次のガイダンスを必要とする場合があります。 詳細については、「 [Windows 10 Enterprise ライセンスを展開](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses#enabling-subscription-activation-with-an-existing-ea)する」を参照してください。<br><br>Azure AD グループベースのライセンスを構成することによって、セキュリティグループを使用して製品ライセンスを割り当てることができます。 詳細については、「 [Azure Active Directory でのグループベースのライセンスに](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)ついて」を参照してください。<br><br>利用可能なライセンスの詳細については、「 [Microsoft 365 ライセンス](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)」を参照してください。
接続 |  すべての microsoft 管理対象デスクトップデバイスでは、企業ネットワークから多数の microsoft サービスエンドポイントへの接続が必要です。<br><br>必要な ip および url の完全な一覧については、「[ネットワーク構成](../get-ready/network.md)」を参照してください。 
Azure Active Directory |    azure Active directory (azure ad) は、すべてのユーザーアカウントの権限を持つ必要があります。または、サポートされている最新バージョンの azure AD Connect を使用して、オンプレミスの Active directory からユーザーアカウントを同期する必要があります。<br><br>azure ad connect の詳細については、「 [azure ad connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)」を参照してください。<br><br>サポートされている azure ad connect のバージョンの詳細については、「 [azure ad connect: バージョンリリース履歴](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)」を参照してください。
認証 |    azure ad がユーザーアカウントの権限元ではない場合は、次のいずれかを azure ad Connect で構成する必要があります。<br>-パスワードハッシュの同期<br>-パススルー認証<br>-ADFS とのフェデレーション<br><br>Azure AD Connect を使用して認証オプションを設定する場合、パスワードの書き戻しも必要になります。 詳細については、「[パスワードの書き戻し](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)」を参照してください。 <br><br>azure ad での認証オプションの詳細については、「 [azure ad Connect ユーザーのサインインオプション](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)」を参照してください。
Office 365 |    Microsoft マネージドデスクトップに登録する必要はありませんが、次のサービスをクラウドに移行することを強くお勧めします。<br>-電子メール-クラウドベースのメールボックス、exchange online、または exchange 2013 以上の exchange online ハイブリッドをオンプレミスで構成します。<br>-ファイルとフォルダー-OneDrive for business/SharePoint Online に移行します。<br>-オンラインコラボレーションツール-Teams への移行。
デバイスの管理 | microsoft マネージドデスクトップデバイスでは、microsoft Intune を使用した管理が必要です。 Intune は、モバイルデバイス管理機関として設定する必要があります。<br><br>詳細については、「 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)」を参照してください。 
データのバックアップと復旧 | Microsoft マネージドデスクトップでは、ファイルを OneDrive for business に同期して保護する必要があります。 OneDrive for business に同期されていないファイルは、Microsoft マネージドデスクトップによって保証されないため、デバイスの交換時に失われる可能性があります。または、デバイスのリセットを必要とするサポート呼び出しもあります。<br><br>必須ではありませんが、Microsoft Managed Desktop は、マップされたネットワークドライブから適切なクラウドソリューションに移行することを強くお勧めします。  

microsoft マネージドデスクトップの使用を開始する準備ができたら、microsoft アカウントマネージャーにお問い合わせください。 
