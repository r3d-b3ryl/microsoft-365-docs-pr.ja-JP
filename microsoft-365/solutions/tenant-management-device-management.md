---
title: 手順 5.  エンタープライズ テナントのMicrosoft 365のデバイスとアプリの管理
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Microsoft 365 テナントのデバイスとアプリの管理に適切なオプションをデプロイします。
ms.openlocfilehash: 09fd96977fbde0f546049d24b1705d27b4c92080
ms.sourcegitcommit: 22cae7ec541268d519d45518c32f22bf5811aec1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2022
ms.locfileid: "62524167"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a>手順 5.  エンタープライズ テナントのMicrosoft 365のデバイスとアプリの管理

企業向けのMicrosoft 365には、デバイスの管理に役立つ機能と、モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) を使用して組織内のデバイスでアプリを使用する機能が含まれています。 iOS、Android、macOS、Windows デバイスを管理して、データを含む組織のリソースへのアクセスを保護できます。 たとえば、メールが組織外のユーザーに送信されないようにしたり、従業員の個人用デバイス上の個人データから組織データを分離したりできます。

ユーザー、デバイス、およびローカルおよびクラウドの生産性アプリ (Microsoft Teamsなど) の使用の検証と管理の例を次に示します。

![ユーザー、デバイス、アプリの検証と管理。](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

組織のリソースをセキュリティで保護するために、企業向けのMicrosoft 365には、デバイスとアプリへのアクセスを管理するのに役立つ機能が含まれています。 デバイス管理には、次の 2 つのオプションがあります。

- Microsoft Intuneは、企業向けの包括的なデバイスとアプリ管理ソリューションです。
- 基本的なモビリティとセキュリティ。これは、組織内のデバイスを管理するためのすべてのMicrosoft 365製品に含まれるIntune サービスのサブセットです。 詳細については、「 [基本的なモビリティとセキュリティの機能」を参照してください](../admin/basic-mobility-security/capabilities.md)。

Microsoft 365 E3または E5 がある場合は、Intuneを使用する必要があります。

## <a name="microsoft-intune"></a>Microsoft Intune

[MICROSOFT INTUNE](/mem/intune/fundamentals/planning-guide)を使用して、MDM または MAM を使用して組織へのアクセスを管理します。 MDM は、ユーザーがデバイスをIntuneに "登録" するときです。 デバイスが登録されると、管理対象デバイスになり、組織のポリシー、ルール、および設定を受け取ることができます。 たとえば、特定のアプリのインストール、パスワード ポリシーの作成、VPN 接続のインストールなどを行うことができます。

自分の個人用デバイスを持つユーザーは、デバイスを登録したり、Intuneや組織のポリシーで管理したりしたくない場合があります。 ただし、組織のリソースとデータを保護する必要があります。 このシナリオでは、MAM を使用してアプリを保護できます。 たとえば、ユーザーがデバイス上のSharePointにアクセスするときに PIN を入力する必要がある MAM ポリシーを使用できます。

また、個人用デバイスと組織所有のデバイスを管理する方法も決定します。 デバイスの用途に応じて、デバイスの扱い方が異なる場合があります。

## <a name="identity-and-device-access-configurations"></a>ID とデバイスのアクセス構成

Microsoft は、セキュリティで保護された生産性の高い従業員を確保するために [、ID とデバイスアクセス](../security/office-365-security/microsoft-365-policies-configurations.md) 用の一連の構成を提供しています。 これらの構成には、次の使用が含まれます。

- Azure AD 条件付きアクセス ポリシー
- Microsoft Intuneデバイス コンプライアンスポリシーとアプリ保護ポリシー
- Azure AD Identity Protection ユーザー リスク ポリシー
- クラウド アプリの追加ポリシー

ユーザー、デバイス、およびローカルおよびクラウドの生産性アプリ (Microsoft Teamsなど) の使用を検証および制限するためのこれらの設定とポリシーの適用例を次に示します。

![ユーザー、デバイス、およびアプリの使用に関する要件と制限に関する ID とデバイスアクセスの構成。](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

デバイス アクセスとアプリ管理については、次の記事の構成を使用します。

- [前提条件](../security/office-365-security/identity-access-prerequisites.md)
- [共通 ID とデバイスのアクセス ポリシー](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a>手順 5 の結果

Microsoft 365 テナントのデバイスとアプリの管理では、ユーザー、デバイス、ローカルおよびクラウドの生産性アプリの使用を検証および制限するためのIntune設定とポリシーを決定しました。

新しい要素が強調表示されたデバイスとアプリの管理Intuneテナントの例を次に示します。

![デバイスとアプリの管理がIntuneテナントの例。](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

この図では、テナントには次のものがあります。

- Intuneに登録されている組織所有のデバイス。
- 登録済みデバイスと個人用デバイスのデバイス ポリシーとアプリ ポリシーをIntuneします。

## <a name="ongoing-maintenance-for-device-and-app-management"></a>デバイスとアプリ管理の継続的なメンテナンス

継続的に、次の操作が必要になる場合があります。 

- デバイス登録を管理します。
- 追加のアプリ、デバイス、セキュリティ要件の設定とポリシーを変更します。