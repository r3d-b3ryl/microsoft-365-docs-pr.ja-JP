---
title: Microsoft Defender for Businessの設定と構成
description: Microsoft Defender for Businessのセットアップと構成プロセスの概要を確認する
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
ms.openlocfilehash: e832a06a27d479bcd9ffecaf00e07b20f55d1042
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2022
ms.locfileid: "64862656"
---
# <a name="set-up-and-configure-microsoft-defender-for-business"></a>Microsoft Defender for Businessの設定と構成

> [!NOTE]
> Microsoft Defender for Businessが[Microsoft 365 Business Premium](../../business-premium/index.md)に含まれるようになりました。 

Microsoft Defender for Businessは、特に中小企業向けに設計された、合理化されたセットアップと構成エクスペリエンスを提供します。 この記事は、プロセス全体のガイドとして使用します。

> [!TIP]
> [セットアップ ウィザード](mdb-use-wizard.md)を使用した場合は、基本的なセットアップ プロセスのいくつかの手順を既に完了しています。 この場合、次のことができます。
> - [その他のデバイスをオンボードする](mdb-onboard-devices.md)
> - [セキュリティ ポリシーと設定を構成する](mdb-configure-security-settings.md)
> - [脆弱性の管理 ダッシュボードにアクセスする](mdb-view-tvm-dashboard.md)

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">セキュリティに関する短いアンケート</a>を受けてください。 ご意見をお寄せください。
>

## <a name="the-setup-and-configuration-process"></a>セットアップと構成プロセス

次の図は、Defender for Business の全体的なセットアップと構成プロセスを示しています。 セットアップ ウィザードを使用した場合は、手順 1 から 3、場合によっては手順 4 を既に完了している可能性があります。 

:::image type="content" source="media/mdb-setup-process-2.png" alt-text="Microsoft Defender for Businessのセットアップと構成プロセス。":::

| 手順  | 記事 | 説明  |
|---------|---------|--------|
| 1 | [要件を確認する](mdb-requirements.md) | Microsoft Defender for Businessの要件 (サポートされているオペレーティング システムを含む) を確認します。 [Microsoft Defender for Business要件](mdb-requirements.md)を参照してください。 |
| 2 | [ロールとアクセス許可を割り当てる](mdb-roles-permissions.md)     | セキュリティ チームのユーザーには、検出された脅威&修復アクションの確認、ポリシーの編集&表示、デバイスのオンボード、レポートの使用などのタスクを実行するためのアクセス許可が必要です。 これらのアクセス許可は、特定のロールを通じて付与できます。 [ロールとアクセス許可の割り当てに関するページを](mdb-roles-permissions.md)参照してください。        |
| 3 | [電子メール通知を設定する](mdb-email-notifications.md) | アラートがトリガーされるか、新しい脆弱性が検出されたときに、電子メール通知を受け取るユーザーを指定できます。 [メール通知を設定するを](mdb-email-notifications.md)参照してください。| 
| 4 | [デバイスのオンボード](mdb-onboard-devices.md)     | Microsoft Defender for Businessは、会社のデバイスをオンボードするためのいくつかのオプションから選択できるように設定されています。 [「Microsoft Defender for Businessにデバイスをオンボードする」を](mdb-onboard-devices.md)参照してください。         |
| 5 | [セキュリティ設定とポリシーを構成する](mdb-configure-security-settings.md) | 簡略化された構成プロセスやMicrosoft エンドポイント マネージャーなど、セキュリティ設定とポリシーを構成するためのいくつかのオプションから選択できます。 [セキュリティ設定とポリシーの構成に関](mdb-configure-security-settings.md)するページを参照してください。 |

## <a name="next-steps"></a>次の手順

[手順 1: Microsoft Defender for Businessの要件を確認する](mdb-requirements.md)に進みます。
