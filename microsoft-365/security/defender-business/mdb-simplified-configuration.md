---
title: Microsoft Defender for Business の簡略化された構成プロセス (プレビュー)
description: Microsoft Defender for Business (プレビュー) の簡略化された構成プロセスについて説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/07/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 1bd11102636696f7aafe781af6d16ae078212d8a
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62463467"
---
# <a name="the-simplified-configuration-process-in-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business の簡略化された構成プロセス (プレビュー)

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐[](https://aka.ms/mdb-preview)々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは最初の一連 [のシナリオで](mdb-tutorials.md#try-these-preview-scenarios)起動し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Microsoft Defender for Business (プレビュー) は、特に中小企業向けに設計された簡略化された構成プロセスを特徴とします。 このエクスペリエンスでは、デバイスのオンボーディングと管理を推測し、ウィザードのようなエクスペリエンスと、組織のデバイスを初日から保護するように設計された既定のポリシーを使用します。 **簡略化された構成プロセスを使用することをお勧めしますが、このオプションに限定されません**。

デバイスのオンボーディングと組織のデバイスのセキュリティ設定の構成に関しては、次の複数のエクスペリエンスから選択できます。 

- Microsoft Defender for Business (プレビュー) の簡略化された構成プロセス (*推奨*) 
- Microsoft エンドポイント マネージャーを含むMicrosoft Intune
- デバイスを管理するための Microsoft 以外のソリューション 

## <a name="what-to-do"></a>操作

1. [セットアップと構成オプションを確認する](#review-your-setup-and-configuration-options)
2. [Defender for Business (プレビュー) の簡略化された構成プロセスの詳細](#why-we-recommend-using-the-simplified-configuration-process)
3. [次の手順に進む](#next-steps)

## <a name="review-your-setup-and-configuration-options"></a>セットアップと構成オプションを確認する

次の表では、各エクスペリエンスについて説明します。
<br/><br/>

| ポータル エクスペリエンス  | 説明  |
|---------|---------|
| Microsoft 365 Defenderポータルでの簡略化された構成エクスペリエンス ([https://security.microsoft.com](https://security.microsoft.com)) <br/>(*これは、ほとんどのお客様に推奨されるオプションです*)  | 簡略化された構成エクスペリエンスには、組織のデバイスを 1 日目から保護するのに役立つ既定のセキュリティ設定とポリシーが含まれています。 このエクスペリエンスを利用して、セキュリティ チームは次のMicrosoft 365 Defenderポータルを使用します。 <br/>- Defender for Business をセットアップして構成する (プレビュー) <br/>- インシデントの表示と管理<br/>- 脅威への対応と軽減<br/>- レポートの表示<br/>- 保留中または完了したアクションを確認する <br/><br/> このポータルは、組織のセキュリティ設定と脅威保護機能のワンストップ ショップです。 簡単なエクスペリエンスを利用して、迅速かつ効率的に作業を開始できます。  また、組織のニーズに合わせて設定を編集したり、新しいポリシーを定義したりすることもできます。<br/><br/>詳細については、「Microsoft Defender for Business (プレビュー)のデバイス ポリシーを表示または編集 [する」を参照してください](mdb-view-edit-policies.md)。 |
| 管理Microsoft エンドポイント マネージャー ([https://endpoint.microsoft.com](https://endpoint.microsoft.com))  | Microsoft エンドポイント マネージャー、Microsoft Intuneデバイスのクラウド ベースのモバイル デバイス管理 (MDM) プロバイダー、およびモバイル アプリケーション管理 (MAM) プロバイダーが含まれます。 <br/><br/>多くの組織では、Intune を使用して、携帯電話、タブレット、ラップトップなどのデバイスを管理しています。 詳細については、「デバイスMicrosoft Intune [MDM および MAM プロバイダーである」を参照してください](/mem/intune/fundamentals/what-is-intune)。 <br/><br/>既にユーザーまたはユーザー Microsoft IntuneをMicrosoft エンドポイント マネージャー、そのソリューションを引き続き使用できます。 |
| Microsoft 以外のデバイス管理ソリューション  | MacOS 用 Jamf や Ansible for Linux など、Microsoft 以外の生産性とデバイス管理ソリューションを使用している場合は、Defender for Business (プレビュー) で引き続きそのソリューションを使用できます。 <br/><br/>デバイスが Defender for Business (プレビュー) にオンボードされている場合、デバイスの状態とアラートがポータルにMicrosoft 365 Defenderされます。 詳細については、「Defender [for Endpoint のオンボーディングと構成ツールのオプション」を参照してください](../defender-endpoint/onboard-configure.md)。<br/><br/>Microsoft 以外のデバイス管理ソリューションを既に使用している場合は、そのソリューションを引き続き使用できます。 |


## <a name="why-we-recommend-using-the-simplified-configuration-process"></a>簡略化された構成プロセスの使用をお勧めする理由

**ほとんどのお客様には、Microsoft Defender for Business (プレビュー)** で簡略化された構成プロセスを使用することをお勧めします。 特に中小企業向けには、構成プロセスが簡素化されています。 Defender for Business (プレビュー) は、技術的な専門知識や特別な知識を必要とせずに、1 日目に組織のデバイスを保護するために設計されています。 既定のセキュリティ設定とポリシーを使用すると、オンボード後すぐにデバイスが保護されます。


Defender for Business (プレビュー) は、セキュリティ設定の構成に時間と労力を節約しながら強力な保護を提供するように設計されています。 このポータルの合理化されたエクスペリエンスMicrosoft 365 Defender、デバイスのオンボードと管理が簡単になります。 さらに、既定のポリシーが含まれているので、組織のデバイスはオンボード後すぐに保護されます。 既定の設定は、現在の状態に保つか、ビジネス ニーズに合わせて変更できます。 必要に応じて、新しいポリシーを追加してデバイスを管理することもできます。

## <a name="next-steps"></a>次の手順

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business に関する短いアンケートをご覧ください</a>。 ご意見をお寄せください。
>

- [Microsoft Defender for Business のセットアップと構成 (プレビュー)](mdb-setup-configuration.md)

- [Microsoft Defender for Business の使用を開始する (プレビュー)](mdb-get-started.md)