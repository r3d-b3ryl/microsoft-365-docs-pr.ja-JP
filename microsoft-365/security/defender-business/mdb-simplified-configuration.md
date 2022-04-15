---
title: Microsoft Defender for Businessの簡略化された構成プロセス
description: Microsoft Defender for Businessの簡略化された構成プロセスについて説明します
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 04/12/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 68ebf170fa351d63e943a2c4c7a920d3e243ddbe
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2022
ms.locfileid: "64862634"
---
# <a name="the-simplified-configuration-process-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessの簡略化された構成プロセス

> [!NOTE]
> Microsoft Defender for Businessが[Microsoft 365 Business Premium](../../business-premium/index.md)に含まれるようになりました。 

Microsoft Defender for Businessは、特に中小企業向けに設計された簡略化された構成プロセスを備えています。 このエクスペリエンスでは、デバイスのオンボードと管理から推測が取り消されます。ウィザードのようなエクスペリエンスと既定のポリシーは、初日から会社のデバイスを保護するように設計されています。 **簡略化された構成プロセスを使用することをお勧めします。ただし、このオプションに限定されるわけではありません**。

デバイスのオンボードと会社のデバイスのセキュリティ設定の構成に関しては、いくつかのエクスペリエンスから選択できます。 

- Microsoft Defender for Businessの簡略化された構成プロセス (*推奨*) 
- Microsoft Intune (Microsoft 365 Business Premiumに含まれる) を含む[Microsoft エンドポイント マネージャー](../../business-premium/index.md)
- デバイスを管理するための Microsoft 以外のソリューション 

## <a name="what-to-do"></a>操作

1. [セットアップオプションと構成オプションを確認する](#review-your-setup-and-configuration-options)

2. [Defender for Business の簡略化された構成プロセスの詳細を確認する](#why-we-recommend-using-the-simplified-configuration-process)

3. [次の手順に進む](#next-steps)

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">セキュリティに関する短いアンケート</a>を受けてください。 ご意見をお寄せください。
>

## <a name="review-your-setup-and-configuration-options"></a>セットアップオプションと構成オプションを確認する

次の表では、各エクスペリエンスについて説明します。

| ポータル エクスペリエンス  | 説明  |
|---------|---------|
| Microsoft 365 Defender ポータルでの簡略化された構成エクスペリエンス ([https://security.microsoft.com](https://security.microsoft.com)) <br/>(*これはほとんどのお客様に推奨されるオプション* です)  | 簡略化された構成エクスペリエンスには、Defender for Business の設定と構成に役立つウィザードのようなエクスペリエンスが含まれています。 簡略化された構成には、Defender for Business にオンボードされるとすぐに会社のデバイスを保護するのに役立つ既定のセキュリティ設定とポリシーも含まれています。 <br/><br/>このエクスペリエンスでは、セキュリティ チームはMicrosoft 365 Defender ポータルを使用して次の操作を行います。 <br/>- Defender for Business のセットアップと構成 <br/>- インシデントの表示と管理<br/>- 脅威への対応と軽減<br/>- レポートを表示する<br/>- 保留中または完了したアクションを確認する <br/><br/> Microsoft 365 Defender ポータルは、会社のセキュリティ設定と脅威保護機能のワンストップ ショップです。 簡略化されたエクスペリエンスを利用して、迅速かつ効率的に作業を開始できます。 詳細については、「[ウィザードを使用してMicrosoft Defender for Businessを設定する](mdb-use-wizard.md)」を参照してください。<br/><br/>また、設定を編集したり、会社のニーズに合わせて新しいポリシーを定義したりできます。<br/><br/>詳細については、「[Microsoft Defender for Businessでデバイス ポリシーを表示または編集](mdb-view-edit-policies.md)する」を参照してください。 |
| Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com))  | Microsoft エンドポイント マネージャーには、Microsoft Intune、アプリとデバイス用のクラウドベースのモバイル デバイス管理 (MDM) およびモバイル アプリケーション管理 (MAM) プロバイダーが含まれます。 [Microsoft 365 Business Premium](../../business-premium/index.md)顧客は既にエンドポイント マネージャーを持っています。 <br/><br/>多くの企業では、携帯電話、タブレット、ノート PC などのデバイスを管理するためにIntuneを使用しています。 詳細については、[デバイスの MDM プロバイダーと MAM プロバイダー Microsoft Intune](/mem/intune/fundamentals/what-is-intune)を参照してください。 <br/><br/>Microsoft IntuneまたはMicrosoft エンドポイント マネージャーを既に使用している場合は、そのソリューションを引き続き使用できます。 |
| Microsoft 以外のデバイス管理ソリューション  | Microsoft 以外の生産性とデバイス管理ソリューションを使用している場合は、引き続き Defender for Business でそのソリューションを使用できます。 <br/><br/>デバイスが Defender for Business にオンボードされると、Microsoft 365 Defender ポータルにデバイスの状態とアラートが表示されます。 詳細については、「 [Defender for Endpoint のオンボードと構成ツールのオプション」を参照してください](../defender-endpoint/onboard-configure.md)。 |


## <a name="why-we-recommend-using-the-simplified-configuration-process"></a>簡略化された構成プロセスを使用することをお勧めする理由

ほとんどのお客様 **は、Microsoft Defender for Businessで簡略化された構成プロセスを使用することをお勧めします**。 簡略化された構成プロセスは、特に中小企業向けに合理化されています。 Defender for Business は、高度な技術的専門知識や特別な知識を必要とせずに、初日に会社のデバイスを保護できるように設計されています。 既定のセキュリティ設定とポリシーを使用すると、デバイスはオンボードされるとすぐに保護されます。

Defender for Business は、セキュリティ設定の構成に要する時間と労力を節約しながら、強力な保護を提供するように設計されています。 Microsoft 365 Defender ポータルの合理化されたエクスペリエンスにより、デバイスのオンボードと管理が簡単になります。 また、会社のデバイスがオンボードされるとすぐに保護されるように、既定のポリシーが含まれています。 既定の設定をそのまま使用することも、ビジネス ニーズに合わせて変更を加えることもできます。 必要に応じて、デバイスを管理するための新しいポリシーを追加することもできます。

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Businessの設定と構成](mdb-setup-configuration.md)
- [Microsoft Defender for Businessを使用した概要](mdb-get-started.md)
