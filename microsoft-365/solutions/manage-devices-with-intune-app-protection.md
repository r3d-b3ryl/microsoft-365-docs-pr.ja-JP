---
title: 手順 1. アプリ保護ポリシーの実装
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: dougeby
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
ms.custom: ''
keywords: ''
description: ''
ms.openlocfilehash: c6cee338f4f2f02d3d74da184be15c13d3230c00
ms.sourcegitcommit: 4af23696ff8b44872330202fe5dbfd2a69d9ddbf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2021
ms.locfileid: "61221090"
---
# <a name="step-1-implement-app-protection-policies"></a>手順 1. アプリ保護ポリシーの実装

Intune アプリ保護ポリシー (APP) は、モバイル アプリケーション管理 (MAM) とも呼ばれ、デバイス自体が管理されていない場合でも企業データを保護します。 これにより、ユーザーが自分のデバイスを管理に "登録" することに抵抗がある職場でも、持ち込み (BYO) デバイスと個人用デバイスを有効にできます。 アプリ保護ポリシーは、指定したアプリ内の企業データを、デバイス上の他のアプリにコピーして貼り付けできないようにするものです。

![アプリ保護ポリシーの作成手順](../media/devices/intune-app-steps.png#lightbox)

この図について:
- アプリを使用すると、Intune は組織データと個人データの間に壁を作成します。 アプリ保護ポリシーは、データへのアクセスを許可するアプリを定義します。
- ユーザーが組織の認証情報でサインインした場合、Intune はアプリ層でポリシーを適用し、個人用アプリに組織のデータをコピーして貼り付けることを防ぎ、このデータへの PIN アクセスを要求します。
- アプリ保護ポリシーを作成した後、条件付きアクセス ポリシーを使用してデータ保護を適用します。 

この構成により、ユーザー エクスペリエンスにほとんど影響を与えることなく、セキュリティの状態を大幅に向上させることができます。  従業員は、Office や Microsoft Teams などの使い慣れたアプリを使用できると同時に、組織はアプリやデバイスに含まれるデータを保護できます。

保護が必要なカスタムの基幹業務アプリケーションがある場合は、現在、アプリ ラッピング ツールを使用して、これらのアプリケーションで APP を有効にできます。 または、Intune アプリ SDK を使用して統合することもできます。 アプリにアプリ保護ポリシーが適用されると、アプリは Intune で管理できるようになり、Intune に管理対象アプリとして認識されます。 Intune を使用して基幹業務アプリケーションを保護する方法の詳細については、「[Microsoft Intune を使用してモバイル アプリケーション管理用にアプリを準備する](/mem/intune/developer/apps-prepare-mobile-application-management)」を参照してください。

## <a name="configuring-mobile-app-protection"></a>モバイル アプリの保護を構成する

このガイダンスは、推奨される[ゼロ トラスト ID およびデバイス アクセス ポリシー](../security/office-365-security/microsoft-365-policies-configurations.md)と緊密に連携しています。 Intune でモバイル アプリ保護ポリシーを作成した後、ID チームと連携して、モバイル アプリ保護を適用する Azure AD で条件付きアクセス ポリシーを構成します。 

この図では、2 つのポリシーを強調表示します (図の下の表にも記載されています)。

[![ゼロトラスト ID とデバイス アクセス ポリシー](../media/devices/identity-device-starting-point.png#lightbox)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/devices/identity-device-starting-point.png)

これらのポリシーを構成するには、[ゼロトラスト ID およびデバイス アクセス ポリシー](../security/office-365-security/microsoft-365-policies-configurations.md)に規定されている推奨ガイダンスと設定を使用します。 以下の表は、Intune および Azure AD でこれらのポリシーを構成する手順に直接リンクしています。


|手順  |ポリシー  |詳細情報  |ライセンス  |
|---------|---------|---------|---------|
|1   |  [アプリケーション保護ポリシー (APP) データ保護の適用](../security/office-365-security/identity-access-policies.md#apply-app-data-protection-policies)       | プラットフォーム (Windows iOS/iPadOS、Android) ごとに 1 つの Intune アプリ保護ポリシー。        | Microsoft 365 E3 または E5        |
|2     | [承認済みアプリとアプリの保護が必要](../security/office-365-security/identity-access-policies.md#require-approved-apps-and-app-protection)       |  iOS、iPadOS、Android を使用してスマートフォンやタブレットにモバイル アプリ保護を適用します。   |  Microsoft 365 E3 または E5       |
| | | | |

## <a name="next-steps"></a>次の手順

[手順 2 に進みます。Intune を使用してデバイスを管理対象に登録します](manage-devices-with-intune-enroll.md)。 