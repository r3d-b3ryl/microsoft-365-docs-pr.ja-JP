---
title: 手順 5.  エンタープライズ テナント向け Microsoft 365 のデバイスとアプリの管理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Microsoft 365 テナントのデバイスとアプリの管理に適切なオプションを展開します。
ms.openlocfilehash: a581af3ec2ec192112656f1919e27f5b05a41cb1
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908585"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a>手順 5.  エンタープライズ テナント向け Microsoft 365 のデバイスとアプリの管理

Microsoft 365 for enterprise には、モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) を使用して、組織内のそれらのデバイスでのデバイスとアプリの使用を管理するのに役立つ機能が含まれています。 iOS、Android、macOS、Windows デバイスを管理して、データを含む組織のリソースへのアクセスを保護できます。 たとえば、組織外のユーザーに電子メールが送信されるのを防ぐか、従業員の個人デバイス上の個人データから組織データを分離できます。

ユーザー、デバイス、Microsoft Teams のようなローカルおよびクラウドの生産性アプリの使用の検証と管理の例を次に示します。

![ユーザー、デバイス、アプリの検証と管理](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

組織のリソースをセキュリティで保護するために、Microsoft 365 for enterprise には、デバイスとアプリへのアクセスを管理するのに役立つ機能が含まれています。 デバイス管理には、次の 2 つのオプションがあります。

- Microsoft Intune は、企業向け包括的なデバイスおよびアプリ管理ソリューションです。
- Basic Mobility and Security は、組織内のデバイスを管理するためのすべての Microsoft 365 製品に含まれる Intune サービスのサブセットです。 詳細については [、「Basic Mobility and Security の機能」を参照してください](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities)。

Microsoft 365 E3 または E5 を使用している場合は、Intune を使用する必要があります。

## <a name="microsoft-intune"></a>Microsoft Intune

MDM または MAM を使用して組織へのアクセスを管理するには [、Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) を使用します。 MDM は、ユーザーが Intune でデバイスを "登録" する場合です。 デバイスが登録された後、デバイスは管理対象デバイスであり、組織のポリシー、ルール、および設定を受け取る可能性があります。 たとえば、特定のアプリのインストール、パスワード ポリシーの作成、VPN 接続のインストールなどです。

自分の個人用デバイスを持つユーザーは、自分のデバイスを登録したり、Intune と組織のポリシーで管理したりしたくない場合があります。 ただし、組織のリソースとデータを保護する必要があります。 このシナリオでは、MAM を使ってアプリを保護できます。 たとえば、デバイス上の SharePoint にアクセスするときにユーザーに PIN の入力を要求する MAM ポリシーを使用できます。

また、個人のデバイスや組織が所有するデバイスを管理する方法も決定します。 デバイスの用途に応じて、デバイスの扱い方が異なる場合があります。

## <a name="identity-and-device-access-configurations"></a>ID とデバイスのアクセス構成

Microsoft では、安全で生産性の高い従業員を確保するために [、ID](../security/office-365-security/microsoft-365-policies-configurations.md) とデバイスへのアクセスに関する一連の構成を提供しています。 これらの構成には、次の使用が含まれます。

- Azure AD 条件付きアクセス ポリシー
- Microsoft Intune デバイスコンプライアンスとアプリ保護ポリシー
- Azure AD Identity Protection ユーザー リスク ポリシー
- クラウド アプリの追加ポリシー

ユーザー、デバイス、および Microsoft Teams のようなローカルおよびクラウド生産性向上アプリの使用を検証および制限するこれらの設定とポリシーの適用例を次に示します。

![ユーザー、デバイス、およびアプリの使用に関する要件と制限に関する ID およびデバイス アクセス構成](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

デバイス アクセスとアプリ管理の場合は、次の記事の構成を使用します。

- [前提条件](../security/office-365-security/identity-access-prerequisites.md)
- [共通 ID とデバイスのアクセス ポリシー](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a>手順 5 の結果

Microsoft 365 テナントのデバイスとアプリの管理では、Intune の設定とポリシーを決定して、ユーザー、デバイス、ローカルとクラウドの生産性アプリの使用を検証および制限します。

次に、新しい要素が強調表示された Intune デバイスとアプリ管理を備えたテナントの例を示します。

![Intune デバイスとアプリ管理を使用したテナントの例](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

この図では、テナントには次の機能があります。

- Intune に登録されている組織が所有するデバイス。
- 登録済みデバイスと個人のデバイスの Intune デバイスポリシーとアプリ ポリシー。

## <a name="ongoing-maintenance-for-device-and-app-management"></a>デバイスとアプリの管理の継続的なメンテナンス

継続的に、次の必要が生じ得る場合があります。 

- デバイスの登録を管理します。
- 追加のアプリ、デバイス、セキュリティ要件に合わせ、設定とポリシーを変更します。
