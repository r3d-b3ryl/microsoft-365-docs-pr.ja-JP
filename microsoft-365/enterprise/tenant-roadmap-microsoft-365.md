---
title: テナントのロードマップMicrosoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: ユーザーのテナントをセットアップするためのロードマップMicrosoft 365。
ms.openlocfilehash: d96d6246bfe38c9e3a5f3aadf04bf5cfe19ccd2f54697141a7c5463c72a6aea2
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53794716"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>テナントのロードマップMicrosoft 365

テナントMicrosoft 365は、組織に割り当てられた一連のサービスです。 通常、このテナントは 1 つ以上のパブリック DNS ドメイン 名に関連付けられるので、さまざまなサブスクリプションとユーザー アカウントに割り当てるライセンスの中央分離コンテナーとして機能します。 詳細については、「サブスクリプション、ライセンス、アカウント、および Microsoft のクラウド 製品のテナント」 [を参照してください](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。

テナントを作成するMicrosoft 365、そのテナントを特定の地理的な場所に割り当てる必要があります。 また、複数の地理的な場所を持つテナントを持ち、テナントをある場所から別の場所に移動できます。

テナントをユーザー、グループ、ライセンス、クラウド アプリの準備を整えるには、テナント構成を慎重に計画して実行する必要があります。

## <a name="set-up-your-microsoft-365-tenant"></a>教育機関向け Microsoft 365 テナントをセットアップする

ネットワークがオンプレミスワーカーとリモート ワーカーの両方に対して Microsoft 365 へのアクセス用に最適化された後、次の大きなタスクは、DNS ドメイン 名、一般的なサービス、およびセキュリティで保護されたユーザー サインインをサポートする id インフラストラクチャ用に Microsoft 365 テナントを計画し、構成します。

### <a name="plan"></a>計画

テナントの実装を計画するには、次の方法を実行します。

- [サブスクリプション、ライセンス、およびサブスクリプション (Azure Azure Active Directory) ADについて](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [サードパーティの SSL 証明書の使い方を理解する](plan-for-third-party-ssl-certificates.md)
- [テナントが Azure Microsoft 365 サービスと統合される方法ADする](integrated-apps-and-azure-ads.md)
- [クライアント アプリのサポートを計画する](microsoft-365-client-support-certificate-based-authentication.md)
- [ハイブリッドモダン認証の使い方を決定する](hybrid-modern-auth-overview.md)
- [2007 Officeおよび 2010 Officeアップグレードを計画する](plan-upgrade-previous-versions-office.md)
- [テナントの分離について](/compliance/assurance/microsoft-365-isolation-controls)

### <a name="deploy"></a>展開

テナントを展開するには、次の方法を実行します。 

- 組織の [DNS ドメイン](../admin/setup/add-domain.md) を追加します。
- [設定[ガイド] の [設定ガイドMicrosoft 365 管理センター。](setup-guides-for-microsoft-365.md)
- ID インフラストラクチャを[構築し、](identity-roadmap-microsoft-365.md)[ユーザー サインインをセキュリティで保護します](microsoft-365-secure-sign-in.md)。

### <a name="move-a-tenants-geographic-locations"></a>テナントの地理的な場所を移動する

Microsoft は、引き続き新しいデータセンターの地理的な場所 (geos) を開き、Microsoft 365します。 これらの新しいデータセンター geos は、顧客の需要と使用状況の増加をサポートするために容量と計算リソースを追加します。 さらに、新しいデータセンター geo では、コア カスタマー データを geo 内に常駐できます。

詳細については、「コア データを新しいデータセンター geos[にMicrosoft 365する」を参照してください](moving-data-to-new-datacenter-geos.md)。


## <a name="deploy-microsoft-365-multi-geo"></a>複数地域Microsoft 365展開する

Microsoft 365 Multi-Geo を使用すれば、組織はその組織の Microsoft 365 のプレゼンスを、その既存のテナント内の複数の地域または国に対して展開することができます。

詳細については、「[Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md)」を参照してください。

## <a name="manage-multiple-microsoft-365-tenants"></a>複数のテナントMicrosoft 365管理する 

oganization に 1 つのテナントを持つことは理想的ですが、複数のテナントを持つ多くの組織の 1 つになる可能性があります。 理由としては、合併や買収、管理上の分離が必要な場合、または分散 IT が必要な場合があります。

複数のテナントがMicrosoft 365場合は、以下の記事を参照してください。

- [テナント間コラボレーション](microsoft-365-inter-tenant-collaboration.md)
- [テナント間でのメールボックスの移行](cross-tenant-mailbox-migration.md)
- [テナントからテナントへの移行](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>次の手順

サブスクリプション、ライセンス、アカウント、 [テナントを使用してテナント計画を開始します](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。