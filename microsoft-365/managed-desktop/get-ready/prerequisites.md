---
title: Microsoft マネージドデスクトップの前提条件
description: ''
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6351dd4696ed21b177dc2789b18c380fba4ebe91
ms.sourcegitcommit: 6b5370cded5d8259c9ed561eed324227f74c410b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2019
ms.locfileid: "36171727"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップの前提条件

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

このトピックでは、Microsoft マネージドデスクトップで成功を保証するために満たす必要のあるインフラストラクチャ要件の概要について説明します。 

Microsoft FastTrack を使用すると、これらの要件を満たし、Microsoft マネージドデスクトップへの参加準備に役立てることができます。 詳細については、「 [Microsoft FastTrack](https://fasttrack.microsoft.com/about)」を参照してください。 

項目 | 前提条件の詳細
--- | ---
ライセンス |Microsoft マネージドデスクトップでは、次のいずれかの Microsoft 365 ライセンスが必要です (または同等)。<br>-Microsoft 365 E5<br>-Microsoft 365 E5 セキュリティアドオンを使用した microsoft 365 E3<br><br>利用可能なライセンスの詳細については、「 [Microsoft 365 ライセンス](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)」を参照してください。
接続 |  すべての Microsoft 管理対象デスクトップデバイスでは、企業ネットワークから多数の Microsoft サービスエンドポイントへの接続が必要です。<br><br>必要な Ip および Url の完全な一覧については、「[ネットワーク構成](../get-ready/network.md)」を参照してください。 
Azure Active Directory |    Azure Active Directory (Azure AD) は、すべてのユーザーアカウントの権限を持つ必要があります。または、サポートされている最新バージョンの Azure AD Connect を使用して、オンプレミスの Active Directory からユーザーアカウントを同期する必要があります。<br><br>[エンタープライズ状態ローミング](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview)は、Microsoft Managed Desktop ユーザーが有効になっている必要があります。<br><br>Azure AD Connect の詳細については、「 [AZURE Ad connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)」を参照してください。<br><br>サポートされている Azure AD Connect のバージョンの詳細については、「 [AZURE Ad connect: バージョンリリース履歴](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)」を参照してください。
認証 |    Azure AD がユーザーアカウントの権限元ではない場合は、次のいずれかを Azure AD Connect で構成する必要があります。<br>-パスワードハッシュの同期<br>-パススルー認証<br>-ADFS とのフェデレーション<br><br>Azure AD Connect を使用して認証オプションを設定する場合は、パスワードの書き戻しもお勧めします。 詳細については、「[パスワードの書き戻し](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)」を参照してください。 <br><br>Azure AD での認証オプションの詳細については、「 [AZURE Ad Connect ユーザーのサインインオプション](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)」を参照してください。
Office 365 |    OneDrive for Business は、Microsoft Managed Desktop ユーザーが有効になっている必要があります。<br><br>Microsoft マネージドデスクトップに登録する必要はありませんが、次のサービスをクラウドに移行することを強くお勧めします。<br>-Email: Exchange 2013 またはそれ以降のオンプレミスで、クラウドベースのメールボックス、Exchange online、または exchange Online ハイブリッドでの構成に移行します。<br>-[ファイルとフォルダー]: OneDrive for Business または SharePoint Online に移行します。<br>-オンラインコラボレーションツール: Teams への移行。
デバイスの管理 | Microsoft マネージドデスクトップデバイスでは、Microsoft Intune を使用した管理が必要です。 Intune は、モバイルデバイス管理機関として設定する必要があります。<br><br>詳細については、「 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)」を参照してください。 
データのバックアップと復旧 | Microsoft マネージドデスクトップでは、ファイルを OneDrive for business に同期して保護する必要があります。 OneDrive for Business に同期されていないファイルは、Microsoft マネージドデスクトップによって保証されず、デバイスの交換中またはデバイスのリセットが必要な呼び出し中に失われる可能性があります。<br><br>必須ではありませんが、Microsoft Managed Desktop は、マップされたネットワークドライブから適切なクラウドソリューションに移行することを強くお勧めします。 

Microsoft マネージドデスクトップの使用を開始する準備ができたら、Microsoft アカウントマネージャーにお問い合わせください。 
