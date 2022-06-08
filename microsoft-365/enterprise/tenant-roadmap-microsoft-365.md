---
title: Microsoft 365 のテナント ロードマップ
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: Microsoft 365 のテナントを設定するためのロードマップ。
ms.openlocfilehash: 5eed55d45e4b34962b08d236f8659cfd2cf209c1
ms.sourcegitcommit: 61bdfa84f2d6ce0b61ba5df39dcde58df6b3b59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2022
ms.locfileid: "65940406"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Microsoft 365 のテナント ロードマップ

Microsoft 365 テナントは、組織に割り当てられているサービスのセットです。 通常、このテナントは 1 つ以上のパブリック DNS ドメイン名に関連付けられ、ユーザー アカウントに割り当てるさまざまなサブスクリプションとその中のライセンスの中央および分離されたコンテナーとして機能します。 詳細については、 [Microsoft のクラウド オファリングのサブスクリプション、ライセンス、アカウント、テナントに関する](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)ページを参照してください。

Microsoft 365 テナントを作成するときは、特定の地理的な場所に割り当てます。 複数の地理的な場所を持つテナントを作成し、テナントをある場所から別の場所に移動することもできます。

テナントをユーザー、グループ、ライセンス、クラウド アプリの準備を整えるには、テナント構成を慎重に計画して実行することが重要です。

## <a name="set-up-your-microsoft-365-tenant"></a>教育機関向け Microsoft 365 テナントをセットアップする

ネットワークがオンプレミスワーカーとリモートワーカーの両方に対して Microsoft 365 へのアクセスに最適化されていることを確認した後、次の大きなタスクでは、DNS ドメイン名、共通サービス、およびセキュリティで保護されたユーザー サインインをサポートする ID インフラストラクチャ用に Microsoft 365 テナントを計画し、構成します。

### <a name="plan"></a>計画

テナントの実装を計画するには:

- [サブスクリプション、ライセンス、および Azure Active Directory (Azure AD) テナントについて](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [サード パーティの SSL 証明書を使用する方法を理解する](plan-for-third-party-ssl-certificates.md)
- [Microsoft 365 テナントと Azure AD サービスの統合方法を理解する](integrated-apps-and-azure-ads.md)
- [クライアント アプリのサポートを計画する](microsoft-365-client-support-certificate-based-authentication.md)
- [ハイブリッド先進認証を使用する方法を決定する](hybrid-modern-auth-overview.md)
- [Office 2007 と Office 2010 のアップグレードを計画する](plan-upgrade-previous-versions-office.md)
- [テナントの分離を理解する](/microsoft-365-isolation-in-microsoft-365?view=o365-worldwide&preserve-view=true)

### <a name="deploy"></a>展開

テナントをデプロイするには: 

- 組織の [DNS ドメインを](../admin/setup/add-domain.md) 追加します。
- [Microsoft 365 管理センターのセットアップ ガイドを使用します](setup-guides-for-microsoft-365.md)。
- [ID インフラストラクチャ](deploy-identity-solution-overview.md)を構築します。

### <a name="move-a-tenants-geographic-locations"></a>テナントの地理的な場所を移動する

Microsoft は、Microsoft 365 サービスの新しいデータセンター地理的場所 (geos) を引き続き開いています。 これらの新しいデータセンター geo では、お客様の需要と使用量の増加をサポートするために、容量とコンピューティング リソースが追加されます。 さらに、新しいデータセンター geo では、コア カスタマー データを geo 内に常駐できます。

詳細については、「 [新しい Microsoft 365 データセンター geo へのコア データの移動](moving-data-to-new-datacenter-geos.md)」を参照してください。


## <a name="deploy-microsoft-365-multi-geo"></a>Microsoft 365 Multi-geo を展開する

Microsoft 365 Multi-Geo を使用すれば、組織はその組織の Microsoft 365 のプレゼンスを、その既存のテナント内の複数の地域または国に対して展開することができます。

詳細については、「[Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md)」を参照してください。

## <a name="manage-multiple-microsoft-365-tenants"></a>複数の Microsoft 365 テナントを管理する 

組織化に 1 つのテナントを持つことが理想的ですが、複数のテナントを持つ多くの組織の 1 つになる可能性があります。 理由には、合併や買収、管理上の分離が必要な場合、または分散型 IT が含まれる場合があります。

複数の Microsoft 365 テナントがある場合は、次の記事を参照してください。

- [テナント間コラボレーション](microsoft-365-inter-tenant-collaboration.md)
- [テナント間でのメールボックスの移行](cross-tenant-mailbox-migration.md)
- [テナントからテナントへの移行](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>次の手順

[サブスクリプション、ライセンス、アカウント、テナントを使用してテナント計画を開始します](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。