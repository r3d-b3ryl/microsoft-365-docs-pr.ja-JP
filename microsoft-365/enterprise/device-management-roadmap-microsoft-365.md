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
ms.openlocfilehash: 1a1bdb449aa1d1ba12cf1de422b3e279df6c1376
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315743"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Microsoft 365 のデバイス管理のロードマップ


Microsoft 365 for enterprise では、組織内のデバイスとアプリを管理するのに役立つ機能が用意されています。 モバイルデバイスを管理することにより、組織のリソースを保護し、保護することができます。

デバイスの管理には2つのオプションがあります。

## <a name="microsoft-intune"></a>Microsoft Intune

Intune は、モバイルデバイス管理 (MDM) またはモバイルアプリケーション管理 (MAM) を使用して、組織へのアクセスを管理するためのオプションを提供します。 MDM は、ユーザーが Intune にデバイスを登録するときに行います。 登録されると、管理対象デバイスであり、組織で使用されているすべてのポリシー、ルール、および設定を受け取ることができます。 たとえば、具体的なアプリをインストールしたり、パスワードポリシーを作成したり、VPN 接続をインストールしたりできます。

独自の個人用デバイスを使用しているユーザーは、デバイスの登録や、Intune およびポリシーによる管理を行わないようにすることができます。 ただし、組織のリソースとデータを保護する必要がある場合もあります。 このシナリオでは、MAM を使用してアプリを保護することができます。 たとえば、ユーザーがデバイス上の SharePoint にアクセスするときに PIN を入力する必要がある MAM ポリシーを使用できます。

また、個人または組織所有のデバイスを管理する方法も決定します。 使用方法に応じて、デバイスを異なる方法で扱うことができます。 

[ここ](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)から開始してください。

## <a name="basic-mobility-and-security"></a>基本的なモビリティとセキュリティ
 
これは Microsoft 365 に組み込まれており、iPhones、Ipad、Androids、Windows phone などのユーザーのモバイルデバイスをセキュリティで保護し、管理することができます。 デバイスのセキュリティ ポリシーを作成および管理したり、リモートでデバイスをワイプしたり、詳細なデバイス レポートを参照できます。 

[ここ](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)から開始してください。
 
## <a name="identity-and-device-access-recommendations"></a>ID とデバイスのアクセスに関する推奨事項

Microsoft では、セキュアで生産性の高い労働力を確保するために [ID とデバイスのアクセス](microsoft-365-policies-configurations.md)に関する一連の推奨事項を提供しています。 デバイスアクセスの場合は、次の記事の推奨事項と設定を使用します。

- [前提条件](identity-access-prerequisites.md)
- [共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Contoso 社が Microsoft 365 のデバイス管理を行った方法

架空の多国籍企業である Contoso Corporation が、Microsoft 365 cloud services を使用して [モバイルデバイス管理インフラストラクチャを展開](contoso-mdm.md) した方法について説明します。
