---
title: Microsoft 365 DefenderのMicrosoft Defender for Identity
description: Microsoft Defender for IdentityからMicrosoft 365 Defenderへの変更について説明します
keywords: Microsoft 365 Defender、Microsoft Defender for Identity、NDI の概要
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dacurwin
author: dcurwin
manager: dansimp
ms.date: 07/06/2022
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.openlocfilehash: 53c43c3196a22a97b2f11105f5145bd62229b137
ms.sourcegitcommit: 9fdb5c5b9eaf0c8a8d62b579a5fb5a5dc2d29fa9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2022
ms.locfileid: "66714815"
---
# <a name="microsoft-defender-for-identity-in-microsoft-365-defender"></a>Microsoft 365 DefenderのMicrosoft Defender for Identity

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender for Identity](/defender-for-identity/)

Microsoft Defender for IdentityがMicrosoft 365 Defenderの一部になりました。 Microsoft 365 Defender ポータルを使用すると、セキュリティ管理者は 1 つの場所でセキュリティ タスクを実行できます。 これにより、ワークフローが簡略化され、他のMicrosoft 365 Defender サービスの機能が追加されます。 Microsoft 365 Defenderは、Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および管理するためのホームです。

Microsoft Defender for Identityは、id に焦点を当てた情報を、Microsoft 365 Defenderが提示するインシデントやアラートに提供します。 この情報は、コンテキストを提供し、Microsoft 365 Defender内の他の製品からのアラートを関連付けるために重要です。

## <a name="quick-reference"></a>クイック リファレンス

次の表に、Microsoft Defender for IdentityとMicrosoft 365 Defender間のナビゲーションの変更を示します。

| **Defender for** Id  | **Microsoft 365 Defender**                                   |
| -------------------------- | ------------------------------------------------------------ |
| タイムライン                   | Microsoft 365 Defender アラート/インシデント キュー                |
| レポート                    | [従来の Defender for Identity ポータル](/defender-for-identity/classic-workspace-portal)に残ります。 <br> カスタマイズされたレポートは、[高度な捜索](#advanced-hunting-new)を使用してMicrosoft 365 Defender ポータルで作成できます。               |
| [ユーザー] ページ                  | Microsoft 365 Defender ユーザー ページ                             |
| [デバイス] ページ                | [デバイスのMicrosoft 365 Defender] ページ                           |
| [グループ] ページ                 | Microsoft 365 Defender グループのサイド ウィンドウ                      |
| [アラート] ページ                 | Microsoft 365 Defender アラート ページ                            |
| 検索                     | Microsoft 365 Defender検索                                |
| ヘルス センター              | 設定 -> ID -> センサー                            |
| エンティティ アクティビティ          | 高度な追及                                             |
| Settings                   | 設定 -> ID                                       |
| ユーザーとアカウント         | 資産 -> ID                                         |
| ID セキュリティ体制  | [Microsoft Defender for Identityのセキュリティ体制評価](/defender-for-identity/security-assessment) |
| 新しいワークスペースのオンボード | 設定 -> ID (自動的)                       |

## <a name="whats-changed"></a>変更内容

### <a name="defender-for-identity-settings"></a>Defender for Identity の設定

Microsoft Defender for Identity構成設定にアクセスするには、[Microsoft 365 Defender](https://security.microsoft.com)の **[設定] と [****ID]** の順に移動します。

### <a name="defender-for-identity-security-posture"></a>Defender for Identity セキュリティ体制

Defender for Cloud Apps で以前にアクセスできたすべての ID セキュリティ体制管理評価は、Microsoft Secure Score で利用できるようになりました<https://security.microsoft.com/securescore>。これは[、Microsoft 365 Defender ポータル](https://security.microsoft.com)にあります。 詳細については、「[Microsoft Defender for Identityのセキュリティ体制の評価](/defender-for-identity/security-assessment)」を参照してください。

### <a name="global-search"></a>グローバル検索

Microsoft 365 Defenderのグローバル検索 (ページ上部の検索バーを使用) を使用すると、セキュリティ チームは、id、エンドポイント、Office 365 データなど、Microsoft 365 Defenderによって監視されているエンティティを検索できます。 検索ドロップダウンから結果を直接操作することも、セキュリティ チームが [ **すべてのユーザー** ] または [ **すべてのデバイス**  ] を選択して、その検索語句に関連付けられているすべてのエンティティを表示することもできます。

### <a name="onboarding-and-administration"></a>オンボードと管理

新しい顧客のオンボード プロセスは自動的に行われ、ワークスペースを手動で構成する必要はありません。 さらに、すべての管理者機能は、Microsoft 365 Defenderの [設定] の [**ID]** メニューで利用できます。

### <a name="alerting-and-incident-correlation"></a>アラートとインシデントの関連付け

Defender for Identity アラートがMicrosoft 365 Defenderのアラート キューに含まれるようになり、自動インシデントの関連付け機能を利用できるようになりました。 これにより、すべてのアラートを 1 か所で使用できるようになり、違反の範囲を以前よりも迅速に特定できます。 詳細については、「[Microsoft 365 Defenderの Defender for Identity セキュリティ アラート](/defender-for-identity/manage-security-alerts)」を参照してください。

### <a name="advanced-hunting-new"></a>高度なハンティング (新規)

高度なハンティング クエリを使用して、脅威と悪意のあるアクティビティを事前に検索できるようになりました。 これらの強力なクエリを使用して、既知の脅威と潜在的な脅威の両方の脅威インジケーターとエンティティを見つけて確認できます。

カスタム検出ルールは、高度なハンティング クエリから構築でき、侵害アクティビティや不適切な構成されたデバイスを示す可能性があるイベントを事前に監視するのに役立ちます。 詳細については、「[Microsoft 365 Defenderでの高度な捜索で脅威をプロアクティブに検出](advanced-hunting-overview.md)する」を参照してください。

### <a name="alert-exclusions-updated"></a>アラートの除外 (更新)

アラート インターフェイスは、便利な検索機能を追加するなど、ユーザー フレンドリです。 さらに、グローバル除外が含まれるようになりました。 つまり、Defender for Identity によって生成されたすべてのアラートから任意のエンティティを除外でき、テストシナリオに役立ちます。 詳細については、「[Microsoft 365 Defenderで Defender for Identity 検出の除外を構成する](/defender-for-identity/exclusions)」を参照してください。

### <a name="entity-profiles"></a>エンティティ プロファイル

Defender for Identity データは、Microsoft 365 ユーザーおよびデバイス エンティティ プロファイルに含まれるようになりました。

### <a name="remediation-actions-new"></a>修復アクション (新規)

アカウントの無効化やパスワードリセットの要求などの Defender for Identity 修復アクションを、Microsoft 365 Defender ユーザー ページから実行できるようになりました。 詳細については、「[Microsoft Defender for Identityの修復アクション](/defender-for-identity/remediation-actions)」を参照してください。

### <a name="lateral-movement-paths"></a>横移動パス

ユーザー ページの **[横移動パス** ] タブに加えて、 **高度なハンティング** 機能と横移動パスのセキュリティ評価を使用して横移動パスを検出することもできます。 詳細については、「[Microsoft Defender for Identity横移動パス (LMP)」を参照](/defender-for-identity/understand-lateral-movement-paths)してください。

## <a name="related-videos"></a>関連するビデオ

- [Microsoft Defender for Identityの新規](https://www.microsoft.com/videoplayer/embed/RE4HcEU)

## <a name="related-information"></a>関連情報

- [Microsoft 365 Defender](microsoft-365-defender.md)
