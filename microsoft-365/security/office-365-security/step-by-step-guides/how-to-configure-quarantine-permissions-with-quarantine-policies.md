---
title: 検疫のアクセス許可とポリシーを構成する方法
description: AdminOnlyPolicy、制限付きアクセス、フル アクセス、誤検知フォルダーを管理する簡単な方法をセキュリティ管理者とユーザーに提供するなど、さまざまなグループで検疫ポリシーとアクセス許可を構成する手順。
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: 709656cafc15333559ac8abe50e21ccde690d09a
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2022
ms.locfileid: "67106955"
---
# <a name="how-to-configure-quarantine-permissions-and-policies"></a>検疫のアクセス許可とポリシーを構成する方法

ハイブリッド作業の進化に伴うより積極的なセキュリティ体制に対する需要の高まりを考えると、セキュリティ管理者とユーザーに偽陽性フォルダーを管理する非常に簡単な方法を提供することが重要です。 規範的なアプローチを取ると、管理者とユーザーは、以下のガイダンスを使用してこれを実現できます。

> [!TIP]
> 検疫のアクセス許可とポリシーを設定しようとしている管理者向けの短いビデオについては、 [このリンクを参照してください](https://www.youtube.com/watch?v=vnar4HowfpY)。 エンド ユーザーの場合は、プロセスのこの [1 分間の概要](https://www.youtube.com/watch?v=s-vozLO43rI) を選択します。

## <a name="what-you-will-need"></a>必要なもの
- 十分なアクセス許可 (セキュリティ管理者ロール)
- 次の手順を実行するには、5 分かかります。

## <a name="creating-custom-quarantine-policies-with-request-release-flow"></a>要求リリース フローを使用したカスタム検疫ポリシーの作成

カスタム ポリシーを使用すると、管理者は、ユーザーが ***False positive** _ フォルダーでトリアージできるアイテムを決定できます。これにより、ユーザーはフォルダーからそれらのアイテムの_release* を要求できるようになります。

1. トリアージではなく、ユーザーがトリアージするアイテムのカテゴリ (一括、スパム、フィッシング、高信頼フィッシング、マルウェア) を決定します。
1. ユーザーがトリアージしたくないカテゴリについては、アイテムを **AdminOnlyPolicy に** 割り当てます。 アクセスが制限されたユーザーをトリアージするカテゴリについては、要求リリース アクセスを使用して *カスタム ポリシーを作成* し、そのカテゴリにユーザーを割り当てることができます。
1. マルウェアと信頼性の高いフィッシングアイテムを **AdminOnlyPolicy に** 割り当てることを **強くお勧めします**。通常の信頼度の高いフィッシングアイテムには *、要求のリリースで制限付きアクセスを* 割り当て、一括およびスパムはユーザーのフル アクセスとして残すことができます。

> [!IMPORTANT]
> 詳細なカスタム ポリシーを作成する方法の詳細については、「[検疫ポリシー - Office 365 |」を参照してください。Microsoft Docs](../../office-365-security/quarantine-policies.md)。

## <a name="assigning-quarantine-policies-and-enabling-notification-with-organization-branding"></a>検疫ポリシーの割り当てと組織のブランド化による通知の有効化

ユーザーがトリアージまたはトリアージできないアイテムのカテゴリが決定され、対応する検疫ポリシーが作成されたら、管理者はこれらのポリシーをそれぞれのユーザーに割り当て、通知を有効にする必要があります。

1. *フル アクセス* カテゴリに含めるユーザー、グループ、またはドメインと *、制限付きアクセス* カテゴリと *管理のみの* カテゴリを特定します。
1. [Microsoft Security ポータル](https://security.microsoft.com)にサインインします。
1. **Email &コラボレーション** > **ポリシー&ルール** を選択します。
1. **[脅威ポリシー**] を選択します。
1. **スパム対策ポリシー**、**フィッシング対策** ポリシー、**マルウェア対策** ポリシーのいずれかを選択します。
1. [ **ポリシーの作成** ] を選択し、[受信] を選択 **します**。
1. ポリシーを適用するポリシー名、ユーザー、グループ、またはドメインを追加し、 **次へ** を追加します。
1. [ **アクション] タブで** 、カテゴリの **[検疫メッセージ]** を選択します。 *検疫ポリシーを選択* するための追加のパネルが表示されます。そのドロップダウンを使用して、前に作成した検疫ポリシーを選択します。
1. **[確認**] セクションに移動し、[**確認**] ボタンをクリックして新しいポリシーを作成します。
1. フィッシング **対策ポリシー**、 **マルウェア** 対策ポリシー、 **安全な添付ファイル** ポリシーという他のポリシーについても、同じ手順を繰り返します。

> [!TIP]
> これまでに学習した内容の詳細については、「[スパム フィルター ポリシーの構成 - Office 365 |」を参照してください。](../../office-365-security/configure-your-spam-filter-policies.md)| [Microsoft Docs EOP でフィッシング対策ポリシーを構成する - Office 365 |](../../office-365-security/configure-anti-phishing-policies-eop.md) |  Microsoft Docs [Configure マルウェア対策ポリシー - Office 365 |](../../office-365-security/configure-anti-malware-policies.md)|  Microsoft Docs Microsoft Defender for Office 365[で安全な添付ファイル ポリシーを設定する - Office 365 |Microsoft Docs](../../office-365-security/set-up-safe-attachments-policies.md)

## <a name="next-steps"></a>次の手順

- 検疫ポリシーで使用できる **グローバル ポリシー** を使用して、組織のブランド ロゴ、表示名、免責事項を有効にします。
- また、検疫通知の **ユーザー頻度を 1 日** に設定します。

## <a name="more-information"></a>詳細

組織のブランド化と通知の設定の詳細については、[検疫ポリシー - Office 365 |Microsoft Docs](../../office-365-security/quarantine-policies.md)
