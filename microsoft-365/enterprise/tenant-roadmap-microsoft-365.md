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
description: Microsoft 365 用のテナントをセットアップするためのロードマップ。
ms.openlocfilehash: 038d9b0d94b84d184f0d9d9b250d0ee4d2c19de9
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753968"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Microsoft 365 のテナントロードマップ

Microsoft 365 テナントは、組織に割り当てられた一連のサービスです。 通常、このテナントは1つ以上のパブリック DNS ドメイン名に関連付けられており、さまざまなサブスクリプションと、ユーザーアカウントに割り当てられたライセンスの間の中央および分離されたコンテナーとして機能します。 詳細については、「 [Microsoft のクラウドサービスのサブスクリプション、ライセンス、アカウント、およびテナント](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)」を参照してください。

Microsoft 365 テナントを作成するときは、特定の地理的な場所に割り当てます。 また、複数の地理的な場所を持つテナントを作成し、テナントをある場所から別の場所に移動することもできます。

テナントのユーザー、グループ、ライセンス、およびクラウドアプリを使用できるようにするには、テナントの構成を慎重に計画して実行することが重要です。

## <a name="set-up-your-microsoft-365-tenant"></a>Microsoft 365 テナントをセットアップする

オンプレミスとリモートの両方のワーカーに対して Microsoft 365 へのアクセスのためにネットワークを最適化することを確認した後、次の大きなタスクでは、DNS ドメイン名、一般的なサービス、およびセキュリティで保護されたユーザーのサインインをサポートするその id インフラストラクチャに対して Microsoft 365 テナントを計画し、構成します。

### <a name="plan"></a>計画

テナントの実装を計画するには、次のようにします。

- [サブスクリプション、ライセンス、および Azure Active Directory (Azure AD) テナントについて理解する](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [サードパーティの SSL 証明書の使用方法を理解する](plan-for-third-party-ssl-certificates.md)
- [Microsoft 365 テナントを Azure AD サービスと統合する方法を理解する](integrated-apps-and-azure-ads.md)
- [クライアントアプリのサポートを計画する](microsoft-365-client-support-certificate-based-authentication.md)
- [ハイブリッド先進認証の使用方法を決定する](hybrid-modern-auth-overview.md)
- [Office 2007 および Office 2010 のアップグレードを計画する](plan-upgrade-previous-versions-office.md)
- [テナントの分離について](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a>展開

テナントを展開するには、次のようにします。 

- 組織の [DNS ドメイン](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) を追加します。
- [Microsoft 365 管理センターのセットアップガイド](setup-guides-for-microsoft-365.md)を使用します。
- [Id インフラストラクチャ](identity-roadmap-microsoft-365.md)を構築し、[ユーザーのサインインをセキュリティで保護](microsoft-365-secure-sign-in.md)します。

### <a name="move-a-tenants-geographic-locations"></a>テナントの地理的な場所を移動する

Microsoft は、Microsoft 365 services の新しいデータセンターの地理的な場所 (geo) を引き続き開きます。 これらの新しいデータセンター geo は、お客様の需要と利用状況の拡大をサポートするための容量とコンピューティングリソースを追加します。 さらに、新しいデータセンター geo では、コア カスタマー データを geo 内に常駐できます。

詳細については、「 [主要データを新しい Microsoft 365 データセンター geo に移行する」を](moving-data-to-new-datacenter-geos.md)参照してください。


## <a name="deploy-microsoft-365-multi-geo"></a>Microsoft 365 複数地域の展開

Microsoft 365 Multi-Geo を使用すれば、組織はその組織の Microsoft 365 のプレゼンスを、その既存のテナント内の複数の地域または国に対して展開することができます。

詳細については、「 [Microsoft 365 複数地域](microsoft-365-multi-geo.md)」を参照してください。

## <a name="manage-multiple-microsoft-365-tenant"></a>複数の Microsoft 365 テナントを管理する 

Oガントの作成に単一のテナントがあると理想的ですが、複数のテナントを持つ多くの組織のうちの1つである場合があります。 その理由として、合併や買収、管理上の分離が必要な場合、または分散化を行う場合があります。

Microsoft 365 テナントが複数ある場合は、次の記事を参照してください。

- [テナント間コラボレーション](microsoft-365-inter-tenant-collaboration.md)
- [テナント間でのメールボックスの移行](cross-tenant-mailbox-migration.md)
- [テナントからテナントへの移行](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>次のステップ

[サブスクリプション、ライセンス、アカウント、テナント](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)を使用して、テナントの計画を開始します。
