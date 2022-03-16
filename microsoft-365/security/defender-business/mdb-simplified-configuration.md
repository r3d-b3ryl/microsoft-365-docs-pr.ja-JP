---
title: Microsoft Defender for Business の簡略化された構成プロセス
description: Microsoft Defender for Business の簡略化された構成プロセスについて説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 5a5b78515176de74fd97430b638782c3e453d917
ms.sourcegitcommit: a216617d6ff27fe7d3089a047fbeaac5d72fd25c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2022
ms.locfileid: "63512742"
---
# <a name="the-simplified-configuration-process-in-microsoft-defender-for-business"></a>Microsoft Defender for Business の簡略化された構成プロセス

> [!IMPORTANT]
> Microsoft Defender for Business は、2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。[](../../business-premium/index.md) スタンドアロン サブスクリプションとしての Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐 [々にロールアウト](https://aka.ms/mdb-preview) されます。 プレビューには最初 [の一連のシナリオが含まれています](mdb-tutorials.md#try-these-preview-scenarios)。定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Microsoft Defender for Business は、特に中小企業向けに設計された、簡略化された構成プロセスを備しています。 このエクスペリエンスでは、デバイスのオンボーディングと管理を推測し、ウィザードのようなエクスペリエンスと、会社のデバイスを初日から保護するように設計された既定のポリシーを使用します。 **簡略化された構成プロセスを使用することをお勧めしますが、このオプションに限定されません**。

デバイスのオンボーディングと会社のデバイスのセキュリティ設定の構成に関しては、次の複数のエクスペリエンスから選択できます。 

- Microsoft Defender for Business の簡略化された構成プロセス (*推奨*) 
- Microsoft エンドポイント マネージャー (Microsoft Intuneに含[まれる) Microsoft 365 Business Premium](../../business-premium/index.md))
- デバイスを管理するための Microsoft 以外のソリューション 

## <a name="what-to-do"></a>操作

1. [セットアップと構成オプションを確認する](#review-your-setup-and-configuration-options)

2. [Defender for Business の簡略化された構成プロセスの詳細](#why-we-recommend-using-the-simplified-configuration-process)

3. [次の手順に進む](#next-steps)

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business に関する短いアンケートをご覧ください</a>。 ご意見をお寄せください。
>

## <a name="review-your-setup-and-configuration-options"></a>セットアップと構成オプションを確認する

次の表では、各エクスペリエンスについて説明します。
<br/><br/>

| ポータル エクスペリエンス  | 説明  |
|---------|---------|
| Microsoft 365 Defenderポータルでの簡略化された構成エクスペリエンス ([https://security.microsoft.com](https://security.microsoft.com)) <br/>(*これは、ほとんどのお客様に推奨されるオプションです*)  | 簡略化された構成エクスペリエンスには、Defender for Business のセットアップと構成に役立つウィザードのようなエクスペリエンスが含まれています。 簡略化された構成には、Defender for Business にオンボードされた会社のデバイスを保護するための既定のセキュリティ設定とポリシーも含まれています。 <br/><br/>このエクスペリエンスを利用して、セキュリティ チームは次のMicrosoft 365 Defenderポータルを使用します。 <br/>- Defender for Business のセットアップと構成 <br/>- インシデントの表示と管理<br/>- 脅威への対応と軽減<br/>- レポートの表示<br/>- 保留中または完了したアクションを確認する <br/><br/> このMicrosoft 365 Defenderポータルは、会社のセキュリティ設定と脅威保護機能のワンストップ ショップです。 簡単なエクスペリエンスを利用して、迅速かつ効率的に作業を開始できます。 詳細については、「ウィザードを [使用して Microsoft Defender for Business をセットアップする」を参照してください](mdb-use-wizard.md)。<br/><br/>また、設定を編集したり、会社のニーズに合わせて新しいポリシーを定義することもできます。<br/><br/>詳細については、「 [Microsoft Defender for Business でデバイス ポリシーを表示または編集する」を参照してください](mdb-view-edit-policies.md)。 |
| 管理Microsoft エンドポイント マネージャー ([https://endpoint.microsoft.com](https://endpoint.microsoft.com))  | Microsoft エンドポイント マネージャーには、Microsoft Intuneデバイスのクラウド ベースのモバイル デバイス管理 (MDM) プロバイダー、およびモバイル アプリケーション管理 (MAM) プロバイダーが含まれます。 [Microsoft 365 Business Premium](../../business-premium/index.md)顧客は既にエンドポイント マネージャー。 <br/><br/>多くの企業では、Intune を使用して、携帯電話、タブレット、ラップトップなどのデバイスを管理しています。 詳細については、「Microsoft Intune [MDM および MAM プロバイダー」を参照してください](/mem/intune/fundamentals/what-is-intune)。 <br/><br/>既にユーザーまたはユーザーのMicrosoft Intune場合Microsoft エンドポイント マネージャー、そのソリューションを引き続き使用できます。 |
| Microsoft 以外のデバイス管理ソリューション  | Microsoft 以外の生産性とデバイス管理ソリューションを使用している場合は、Defender for Business で引き続きそのソリューションを使用できます。 <br/><br/>デバイスが Defender for Business にオンボードされている場合、デバイスの状態とアラートがポータルにMicrosoft 365 Defenderされます。 詳細については、「Defender [for Endpoint のオンボーディングと構成ツールのオプション」を参照してください](../defender-endpoint/onboard-configure.md)。 |


## <a name="why-we-recommend-using-the-simplified-configuration-process"></a>簡略化された構成プロセスの使用をお勧めする理由

**ほとんどのお客様には、Microsoft Defender for Business** で簡略化された構成プロセスを使用することをお勧めします。 特に中小企業向けには、構成プロセスが簡素化されています。 Defender for Business は、技術的な専門知識や特別な知識を必要とせずに、1 日目に会社のデバイスを保護するために設計されています。 既定のセキュリティ設定とポリシーを使用すると、オンボード後すぐにデバイスが保護されます。

Defender for Business は、セキュリティ設定の構成に時間と労力を節約しながら、強力な保護を提供するように設計されています。 モバイル ポータルでの合理化されたエクスペリエンスMicrosoft 365 Defender、デバイスのオンボードと管理が簡単になります。 さらに、既定のポリシーが含まれているので、会社のデバイスはオンボード後すぐに保護されます。 既定の設定は、現在の状態に保つか、ビジネス ニーズに合わせて変更できます。 必要に応じて、新しいポリシーを追加してデバイスを管理することもできます。

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Business のセットアップと構成](mdb-setup-configuration.md)

- [Microsoft Defender for Business の使用を開始する](mdb-get-started.md)
