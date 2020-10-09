---
title: Microsoft 365 のデバイス管理のロードマップ
keywords: Microsoft 365、Microsoft 365 for enterprise、Microsoft 365 ドキュメント、モバイルデバイス管理、Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: Microsoft 365 のデバイス管理をセットアップするためのロードマップ。
ms.openlocfilehash: d359cae62fbd1bf2468ad753670ff8e385d6f25b
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398963"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Microsoft 365 のデバイス管理のロードマップ

Microsoft 365 for enterprise では、組織内のデバイスとアプリを管理するのに役立つ機能が用意されています。 モバイルデバイスを管理することにより、組織のリソースを保護し、保護することができます。

デバイス管理には、次の2つのオプションがあります。

- [Microsoft Intune](#microsoft-intune)
- [基本的なモビリティとセキュリティ](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

Microsoft Intune を使用して、モバイルデバイス管理またはモバイルアプリケーション管理を使用して、組織へのアクセスを管理できます。 モバイルデバイスの管理は、ユーザーが Intune にデバイスを登録するときに行います。 登録されたデバイスは、管理されたデバイスです。そのため、組織のポリシー、ルール、および設定を受信することができます。 たとえば、特定のアプリをインストールしたり、パスワードポリシーを作成したり、VPN 接続をインストールしたりできます。

独自の個人用デバイスを使用しているユーザーは、自分のデバイスを登録したり、Intune および組織のポリシーによって管理したりすることは望まない場合があります。 ただし、組織のリソースとデータを保護する必要がある場合もあります。 このシナリオでは、モバイルアプリケーション管理を使用してアプリを保護することができます。 たとえば、モバイルアプリケーション管理ポリシーを使用して、ユーザーがデバイス上の SharePoint Online にアクセスするときに PIN を入力するよう要求することができます。

また、個人デバイスおよび組織所有のデバイスを管理する方法を決定します。 使用方法に応じて、デバイスを異なる方法で扱うことができます。

## <a name="basic-mobility-and-security"></a>基本的なモビリティとセキュリティ

これは Microsoft 365 に組み込まれており、iPhones、Ipad、Androids、Windows phone などのユーザーのモバイルデバイスをセキュリティで保護し、管理することができます。 デバイスのセキュリティ ポリシーを作成および管理したり、リモートでデバイスをワイプしたり、詳細なデバイス レポートを参照できます。

## <a name="choose-between-the-two-options"></a>2つのオプションのどちらかを選択する

どのデバイス管理オプションが最適かを判断するために、「 [基本モビリティセキュリティと Intune の選択](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune)」を参照してください。

評価に基づき、次のものを使用してデバイスの管理を始めることができます。

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)。
- [基本的なモビリティとセキュリティ](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)。
 
## <a name="identity-and-device-access-recommendations"></a>ID とデバイスのアクセスに関する推奨事項

Microsoft では、セキュアで生産性の高い労働力を確保するために [ID とデバイスのアクセス](../security/office-365-security/microsoft-365-policies-configurations.md)に関する一連の推奨事項を提供しています。 デバイスアクセスの場合は、次の記事の推奨事項と設定を使用します。

- [前提条件](../security/office-365-security/identity-access-prerequisites.md)
- [共通 ID とデバイスのアクセス ポリシー](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Contoso 社が Microsoft 365 のデバイス管理を行った方法

架空の典型的な多国籍企業が Microsoft 365 cloud services を使用してモバイルデバイス管理インフラストラクチャを展開する方法については、「 [mobile device management For Contoso](contoso-mdm.md)」を参照してください。
