---
title: Microsoft 365 のテナントロードマップ
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
description: Microsoft 365 のテナントをセットアップするためのロードマップ。
ms.openlocfilehash: fb3b6eecd893a5ab9b71bfa7bdfaea53af43470d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909456"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Microsoft 365 のテナントロードマップ

Microsoft 365 テナントは、組織に割り当てられたサービスのセットです。 通常、このテナントは 1 つ以上のパブリック DNS ドメイン 名に関連付けられるので、さまざまなサブスクリプションとユーザー アカウントに割り当てるライセンスの中央分離コンテナーとして機能します。 詳細については、「サブスクリプション、ライセンス、アカウント、および Microsoft のクラウド 製品のテナント」 [を参照してください](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。

Microsoft 365 テナントを作成すると、そのテナントを特定の地理的な場所に割り当てる必要があります。 また、複数の地理的な場所を持つテナントを持ち、テナントをある場所から別の場所に移動できます。

テナントをユーザー、グループ、ライセンス、クラウド アプリの準備を整えるには、テナント構成を慎重に計画して実行する必要があります。

## <a name="set-up-your-microsoft-365-tenant"></a>教育機関向け Microsoft 365 テナントをセットアップする

ネットワークがオンプレミスワーカーとリモート ワーカーの両方に対して Microsoft 365 へのアクセス用に最適化された後、次の大きなタスクは、microsoft 365 テナントを DNS ドメイン 名、一般的なサービス、およびセキュリティで保護されたユーザー サインインをサポートする ID インフラストラクチャ用に計画し、構成します。

### <a name="plan"></a>計画

テナントの実装を計画するには、次の方法を実行します。

- [サブスクリプション、ライセンス、および Azure Active Directory (Azure Active Directory) テナントAD理解する](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [サードパーティの SSL 証明書の使い方を理解する](plan-for-third-party-ssl-certificates.md)
- [Microsoft 365 テナントと Azure サービスの統合方法ADする](integrated-apps-and-azure-ads.md)
- [クライアント アプリのサポートを計画する](microsoft-365-client-support-certificate-based-authentication.md)
- [ハイブリッドモダン認証の使い方を決定する](hybrid-modern-auth-overview.md)
- [2007 Office 2010 年のアップグレードOffice計画する](plan-upgrade-previous-versions-office.md)
- [テナントの分離について](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a>展開

テナントを展開するには、次の方法を実行します。 

- 組織の [DNS ドメイン](../admin/setup/add-domain.md) を追加します。
- Microsoft [365 管理センターのセットアップ ガイドを使用します](setup-guides-for-microsoft-365.md)。
- ID インフラストラクチャを[構築し、](identity-roadmap-microsoft-365.md)[ユーザー サインインをセキュリティで保護します](microsoft-365-secure-sign-in.md)。

### <a name="move-a-tenants-geographic-locations"></a>テナントの地理的な場所を移動する

Microsoft は、Microsoft 365 サービスの新しいデータセンター地理的な場所 (geos) を引き続き開きます。 これらの新しいデータセンター geos は、顧客の需要と使用状況の増加をサポートするために容量と計算リソースを追加します。 さらに、新しいデータセンター geo では、コア カスタマー データを geo 内に常駐できます。

詳細については、「コア データを [新しい Microsoft 365](moving-data-to-new-datacenter-geos.md)データセンター geos に移動する」を参照してください。


## <a name="deploy-microsoft-365-multi-geo"></a>Microsoft 365 Multi-Geo の展開

Microsoft 365 Multi-Geo を使用すれば、組織はその組織の Microsoft 365 のプレゼンスを、その既存のテナント内の複数の地域または国に対して展開することができます。

詳細については、「[Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md)」を参照してください。

## <a name="manage-multiple-microsoft-365-tenants"></a>複数の Microsoft 365 テナントを管理する 

oganization に 1 つのテナントを持つことは理想的ですが、複数のテナントを持つ多くの組織の 1 つになる可能性があります。 理由としては、合併や買収、管理上の分離が必要な場合、または分散 IT が必要な場合があります。

複数の Microsoft 365 テナントがある場合は、以下の記事を参照してください。

- [テナント間コラボレーション](microsoft-365-inter-tenant-collaboration.md)
- [テナント間でのメールボックスの移行](cross-tenant-mailbox-migration.md)
- [テナントからテナントへの移行](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>次の手順

サブスクリプション、ライセンス、アカウント、 [テナントを使用してテナント計画を開始します](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。