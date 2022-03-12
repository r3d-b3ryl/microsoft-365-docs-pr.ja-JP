---
title: Microsoft Defender for Business のセットアップと構成
description: Microsoft Defender for Business のセットアップと構成プロセスの概要を確認する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/24/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: ec001f0a1576b767f93d74b7ef865e3912d397f1
ms.sourcegitcommit: 2697938d2d4fec523b501c5e7b0b8ec8f34e59b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2022
ms.locfileid: "63449794"
---
# <a name="set-up-and-configure-microsoft-defender-for-business"></a>Microsoft Defender for Business のセットアップと構成

> [!IMPORTANT]
> Microsoft Defender for Business は、2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。[](../../business-premium/index.md) スタンドアロン サブスクリプションとしての Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐 [々にロールアウト](https://aka.ms/mdb-preview) されます。 プレビューには最初 [の一連のシナリオが含まれています](mdb-tutorials.md#try-these-preview-scenarios)。定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Microsoft Defender for Business は、特に中小規模ビジネス向けに設計された、合理化されたセットアップと構成エクスペリエンスを提供します。 この記事をガイドとして使用します。

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business に関する短いアンケートをご覧ください</a>。 ご意見をお寄せください。
>

## <a name="the-setup-and-configuration-process"></a>セットアップと構成プロセス

:::image type="content" source="media/mdb-setup-process-2.png" alt-text="Microsoft Defender for Business のセットアップと構成プロセス。":::

| 手順  | 記事 | 説明  |
|---------|---------|--------|
| 1 | [要件を確認する](mdb-requirements.md) | Microsoft Defender for Business のサポートされているオペレーティング システムを含む要件を確認します。 「 [Microsoft Defender for Business の要件」を参照してください](mdb-requirements.md)。 |
| 2 | [役割とアクセス許可の割り当て](mdb-roles-permissions.md)     | セキュリティ チームのユーザーには、検出された脅威& 修復アクションの確認、& 編集ポリシーの表示、デバイスのオンボーディング、レポートの使用など、タスクを実行するためのアクセス許可が必要です。 これらのアクセス許可は、特定の役割を通じて付与できます。 「ロール [とアクセス許可の割り当て」を参照してください](mdb-roles-permissions.md)。        |
| 3 | [電子メール通知を設定する](mdb-email-notifications.md) | アラートがトリガーされた場合、または新しい脆弱性が検出された場合に電子メール通知を受け取るユーザーを指定できます。 「メール [通知を設定する」を参照してください](mdb-email-notifications.md)。| 
| 4 | [デバイスのオンボード](mdb-onboard-devices.md)     | Microsoft Defender for Business は、組織のデバイスをオンボードするためのいくつかのオプションから選択できるようセットアップされています。 「 [オンボード デバイスから Microsoft Defender for Business」を参照してください](mdb-onboard-devices.md)。         |
| 5 | [セキュリティ設定とポリシーを構成する](mdb-configure-security-settings.md) | 複数のオプションから選択して、簡略化された構成プロセスやセキュリティ ポリシーなど、セキュリティ設定とポリシーを構成Microsoft エンドポイント マネージャー。 「 [セキュリティ設定とポリシーを構成する」を参照してください](mdb-configure-security-settings.md)。 |

## <a name="next-steps"></a>次の手順

次の手順に進みます。

- [手順 1: Microsoft Defender for Business の要件を確認する](mdb-requirements.md)
