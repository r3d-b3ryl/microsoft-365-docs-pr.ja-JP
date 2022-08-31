---
title: Microsoft Defender for Businessの設定と構成
description: Defender for Business のサイバーセキュリティ ソリューションを設定する方法について説明します。 デバイスをオンボードし、ポリシーを確認し、必要に応じて設定を編集します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.date: 08/09/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365solution-mdb-setup
- highpri
ms.openlocfilehash: 3c2f22cb7ec397847fb25adaa485588386b62e5c
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481044"
---
# <a name="set-up-and-configure-microsoft-defender-for-business"></a>Microsoft Defender for Businessの設定と構成

Defender for Business は、特に中小企業向けに設計された、合理化されたセットアップと構成エクスペリエンスを提供します。 この記事は、プロセス全体のガイドとして使用します。

> [!TIP]
> [セットアップ ウィザード](mdb-use-wizard.md)を使用した場合は、基本的なセットアップ プロセスのいくつかの手順を既に完了しています。 この場合、次のことができます。
> - [その他のデバイスをオンボードする](mdb-onboard-devices.md)
> - [セキュリティ ポリシーと設定を構成する](mdb-configure-security-settings.md)
> - [Microsoft Defender 脆弱性の管理 ダッシュボードにアクセスする](mdb-view-tvm-dashboard.md)


## <a name="the-setup-and-configuration-process"></a>セットアップと構成プロセス

次の図は、Defender for Business の全体的なセットアップと構成プロセスを示しています。 セットアップ ウィザードを使用した場合は、手順 1 から 3、場合によっては手順 4 を既に完了している可能性があります。 

:::image type="content" source="media/mdb-setup-process-2.png" alt-text="Defender for Business.のセットアップと構成プロセス。":::

| 手順  | 記事 | 説明  |
|---------|---------|--------|
| 1 | [要件を確認する](mdb-requirements.md) | Defender for Business のサポートされているオペレーティング システムを含む要件を確認します。 [Defender for Business の要件を](mdb-requirements.md)参照してください。 |
| 2 | [ロールとアクセス許可を割り当てる](mdb-roles-permissions.md)     | セキュリティ チームのPeopleには、検出された脅威&修復アクションの確認、ポリシーの編集&表示、デバイスのオンボード、レポートの使用など、タスクを実行するためのアクセス許可が必要です。 これらのアクセス許可は、特定のロールを通じて付与できます。 [ロールとアクセス許可の割り当てに関するページを](mdb-roles-permissions.md)参照してください。        |
| 3 | [電子メール通知を設定する](mdb-email-notifications.md) | アラートがトリガーされるか、新しい脆弱性が検出されたときに、電子メール通知を受け取るユーザーを指定できます。 [メール通知を設定するを](mdb-email-notifications.md)参照してください。| 
| 4 | [デバイスのオンボード](mdb-onboard-devices.md)     | ダウンロード可能なスクリプトの使用や、Microsoft Intuneへのデバイスの登録など、会社のデバイスをオンボードするためのいくつかのオプションから選択できます。 [「Defender for Business にデバイスをオンボードする」を](mdb-onboard-devices.md)参照してください。         |
| 5 | [セキュリティ設定とポリシーを構成する](mdb-configure-security-settings.md) | Defender for Business やMicrosoft Intuneの[簡略化された構成プロセス](mdb-simplified-configuration.md)など、セキュリティ設定とポリシーを構成するためのいくつかのオプションから選択できます。 [セキュリティ設定とポリシーの構成に関](mdb-configure-security-settings.md)するページを参照してください。 |

## <a name="next-steps"></a>次の手順

[手順 1: Microsoft Defender for Businessの要件を確認する](mdb-requirements.md)に進みます。
