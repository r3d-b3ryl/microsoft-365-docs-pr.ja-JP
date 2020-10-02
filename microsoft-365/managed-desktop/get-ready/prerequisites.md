---
title: Microsoft マネージド デスクトップの前提条件
description: Microsoft マネージドデスクトップに登録する前に設定するライセンス、Azure アカウント、認証設定、および Microsoft 365 設定
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d5aaba3d1f8606ab69b360d5916a5c9a8a653a14
ms.sourcegitcommit: e87015bf29ad15688137c785d93f2c79ca3208f4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "48343285"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップの前提条件

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

このトピックでは、Microsoft マネージドデスクトップで成功を保証するために満たす必要のあるインフラストラクチャ要件の概要について説明します。 


分野 | 前提条件の詳細
--- | ---
ライセンス |Microsoft マネージドデスクトップでは、エンドポイントと Azure Active Directory Premium 2 (または同等のもの) に対して microsoft Defender に microsoft 365 E3 ライセンスが必要です。<br>特定のサービスプランの詳細については、このトピックの「 [ライセンスについ](#more-about-licenses) て」を参照してください。<br>利用可能なライセンスの詳細については、「 [Microsoft 365 ライセンス](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)」を参照してください。
接続 |  すべての Microsoft 管理対象デスクトップデバイスでは、企業ネットワークから多数の Microsoft サービスエンドポイントへの接続が必要です。<br><br>必要な Ip および Url の完全な一覧については、「 [ネットワーク構成](../get-ready/network.md)」を参照してください。 
Azure Active Directory |    Azure Active Directory (Azure AD) は、すべてのユーザーアカウントの権限を持つ必要があります。または、サポートされている最新バージョンの Azure AD Connect を使用して、オンプレミスの Active Directory からユーザーアカウントを同期する必要があります。<br><br>[エンタープライズ状態ローミング](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) は、Microsoft Managed Desktop ユーザーが有効になっている必要があります。<br><br>詳細については、「 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)」を参照してください。<br><br>サポートされている Azure AD Connect のバージョンの詳細については、「 [AZURE Ad connect: バージョンリリース履歴](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)」を参照してください。
認証 |    Azure AD がユーザーアカウントのプライマリ認証のソースではない場合は、次のいずれかを Azure AD Connect で構成する必要があります。<br>-パスワードハッシュの同期<br>-パススルー認証<br>-Azure AD 統合の要件を満たすように構成された外部 id プロバイダー (Windows Server ADFS および Microsoft 以外の IDPs を含む)。 詳細については、 [ガイドライン](https://www.microsoft.com/download/details.aspx?id=56843) を参照してください。 <br><br>Azure AD Connect を使用して認証オプションを設定する場合は、パスワードの書き戻しもお勧めします。 詳細については、「 [パスワードの書き戻し](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)」を参照してください。 <br><br>外部 id プロバイダーが実装されている場合は、ソリューションを検証する必要があります。<br>-Azure AD 統合の要件を満たす<br>-Azure AD 条件付きアクセスをサポートします。これは、MMD デバイスコンプライアンスポリシーを構成できるようにするためです<br>-Microsoft 365 サービスまたは microsoft マネージドデスクトップの一部として必要な機能のデバイスの登録と使用を可能にする <br><br>Azure AD での認証オプションの詳細については、「 [AZURE Ad Connect ユーザーのサインインオプション](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)」を参照してください。
Microsoft 365 | OneDrive for Business は、Microsoft Managed Desktop ユーザーが有効になっている必要があります。<br><br>Microsoft マネージドデスクトップに登録する必要はありませんが、次のサービスをクラウドに移行することを強くお勧めします。<br>-Email: Exchange 2013 またはそれ以降のオンプレミスで、クラウドベースのメールボックス、Exchange online、または exchange Online ハイブリッドでの構成に移行します。<br>-[ファイルとフォルダー]: OneDrive for Business または SharePoint Online に移行します。<br>-オンラインコラボレーションツール: Teams への移行。
デバイスの管理 | Microsoft マネージドデスクトップデバイスでは、Microsoft Intune を使用した管理が必要です。 Intune は、モバイルデバイス管理機関として設定する必要があります。<br><br>詳細については、「 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)」を参照してください。 
データのバックアップと復元 |  Microsoft マネージドデスクトップでは、ファイルを OneDrive for business に同期して保護する必要があります。 OneDrive for Business に同期されていないファイルは、Microsoft マネージドデスクトップによって保証されず、デバイスの交換中またはデバイスのリセットが必要な呼び出し中に失われる可能性があります。<br><br>必須ではありませんが、Microsoft Managed Desktop は、マップされたネットワークドライブから適切なクラウドソリューションに移行することを強くお勧めします。 詳細については、「 [Microsoft マネージデスクトップのマップされたドライブの準備](mapped-drives.md)」を参照してください。

Microsoft マネージドデスクトップの使用を開始する準備ができたら、Microsoft アカウントマネージャーにお問い合わせください。 

## <a name="more-about-licenses"></a>ライセンスの詳細

Microsoft マネージドデスクトップでは、機能するために特定のライセンスオプションが必要になります。 これらのライセンスの使用方法については、「 [Microsoft Managed Desktop technologies](../intro/technologies.md) 」を参照してください。

> [!TIP]
> これらのライセンスオプションを特定のユーザーに割り当てるには、Azure Active Directory の [グループベースのライセンス機能](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) を活用することをお勧めします。

- Azure Active Directory Premium P2
- Microsoft Intune 
- Windows 10 Enterprise  
- エンドポイントの Microsoft Defender
- Microsoft 365 Apps for enterprise
- Microsoft Teams
- [SharePoint Online プラン 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online プラン 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> Microsoft アカウントマネージャーは、現在のライセンスとサービスプランを確認し、必要な追加ライセンスまたはサービスプランを取得して、重複を回避するために、最も効率的なパスを見つけるのに役立ちます。
