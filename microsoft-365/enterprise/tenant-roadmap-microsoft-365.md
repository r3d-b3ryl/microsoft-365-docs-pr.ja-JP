---
title: Microsoft 365 のテナントロードマップ
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom: it-pro
description: Microsoft 365 用のテナントをセットアップするためのロードマップ。
ms.openlocfilehash: 540d1bc53ac06b85d22a8a60a62e51761e10339c
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315755"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Microsoft 365 のテナントロードマップ

Microsoft 365 テナントは、組織に割り当てられた一連のサービスです。 このテナントは、通常、1つ以上の DNS ドメイン名に関連付けられており、さまざまなサブスクリプションのための中央のコンテナーとして機能し、ユーザーアカウントに割り当てられているライセンスに含まれるものとして機能します。 

Microsoft 365 テナントを作成するときは、特定の地理的な場所に割り当てます。 また、複数の地理的な場所を持つテナントを作成し、テナントをある場所から別の場所に移動することもできます。

ネットワークと id の基本的なサービスを準備するには、適切に計画され、実行されるテナントの構成が重要です。

## <a name="plan"></a>計画

テナントの実装を計画するには、次のようにします。

- [サブスクリプション、ライセンス、および Azure Active Directory (Azure AD) テナントについて理解する](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [サードパーティの SSL 証明書の使用方法を理解する](plan-for-third-party-ssl-certificates.md)
- [Microsoft 365 管理センターでのセットアップガイドへのアクセス](setup-guides-for-microsoft-365.md)
- [Microsoft 365 テナントを Azure AD サービスと統合する方法を理解する](integrated-apps-and-azure-ads.md)
- [クライアントアプリのサポートを計画する](microsoft-365-client-support-certificate-based-authentication.md)
- [ハイブリッド先進認証の使用方法を決定する](hybrid-modern-auth-overview.md)
- [Office 2007 および Office 2010 のアップグレードを計画する](plan-upgrade-previous-versions-office.md)
- [テナントの分離について](microsoft-365-tenant-isolation-overview.md)
- [Microsoft 365 サービスアシュアランスの詳細を取得する](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a>展開

テナントを展開するには、組織の [DNS ドメインを追加](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) します。

## <a name="tenants-with-multiple-geographic-locations"></a>複数の地理的な場所を持つテナント

Microsoft 365 Multi-Geo を使用すれば、組織はその組織の Microsoft 365 のプレゼンスを、その既存のテナント内の複数の地域または国に対して展開することができます。

Microsoft 365 複数地域を使用して、理解、計画、構成、管理を[開始](microsoft-365-multi-geo.md)します。

## <a name="move-a-tenants-geographic-locations"></a>テナントの地理的な場所を移動する

Microsoft は、Microsoft 365 services の新しいデータセンターの地理的な場所 (geo) を引き続き開きます。 これらの新しいデータセンター geo は、お客様の需要と利用状況の拡大をサポートするための容量とコンピューティングリソースを追加します。 さらに、新しいデータセンター geo では、コア カスタマー データを geo 内に常駐できます。

[コアデータを新しい Microsoft 365 データセンター geo に移行する](moving-data-to-new-datacenter-geos.md)ことで、geo データの移行について理解し、要求する作業を開始します。

## <a name="next-step"></a>次の手順

[サブスクリプション、ライセンス、アカウント、テナント](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)を使用して、テナントの計画を開始します。

