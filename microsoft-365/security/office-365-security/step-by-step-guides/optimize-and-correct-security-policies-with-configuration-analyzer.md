---
title: 構成アナライザーを使用してセキュリティ ポリシーを最適化および修正する
description: 構成アナライザーを使用してセキュリティ ポリシーを最適化および修正する手順。 構成アナライザーは、テナントで構成した電子メール セキュリティ ポリシーを管理および表示するための中央の場所と 1 つのウィンドウです。
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
ms.openlocfilehash: 765eaffd2f57687c0ee16ace30aff97ddd91462c
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66994265"
---
# <a name="optimize-and-correct-security-policies-with-configuration-analyzer"></a>構成アナライザーを使用してセキュリティ ポリシーを最適化および修正する

構成アナライザーは、テナントで構成した電子メール セキュリティ ポリシーを管理および表示するための中央の場所と 1 つのウィンドウです。 設定を Standard および Strict の推奨設定と左右に比較し、推奨事項を適用し、姿勢に影響を与えた履歴変更を表示できます。

## <a name="what-youll-need"></a>必要なもの
- Exchange Online Protection
- 十分なアクセス許可 (セキュリティ管理者ロール)
- 次の手順を実行するには、5 分かかります。

## <a name="compare-settings-and-apply-recommendations"></a>設定を比較し、推奨事項を適用する
1. [https://security.microsoft.com/configurationAnalyzer](https://security.microsoft.com/configurationAnalyzer) に移動します。
1. 作成するサイドツーサイドの比較に基づいて、上部のメニューから **[標準の推奨事項** ] または [ **厳密な推奨事項** ] を選択します。
1. ポリシー変更に関する推奨事項が表示されます。 (該当する場合)
1. その後、推奨事項を選択し、推奨されるアクション、推奨事項が適用されるポリシー、現在の構成&名前の設定などに注意してください。
1. 推奨事項を選択した状態で、[ **推奨事項の適用]** を押し、表示される確認メッセージで **[OK] を押します** 。
1. ポリシーを手動で編集する場合、またはポリシー内で設定を直接確認する場合は、新しいタブを読み込み、影響を受けるポリシーに直接移動して、ポリシーを **適用** する代わりにポリシーの **表示** を押すことができます。

## <a name="view-historical-configuration-changes"></a>構成の変更履歴を表示する

**Configuration Analyzer** では、上部のメニュー バーから **[構成ドリフトの分析と履歴**] を選択できます。

読み込まれるページには、フィルターによって選択された時間枠内のセキュリティ ポリシーの変更と、変更に関するデータ、および全体的な姿勢が増減した場合の変更が表示されます。

Configuration Analyzer の詳細については、「[セキュリティ ポリシーの構成アナライザー - Office 365 |」を参照してください。Microsoft Docs](../../office-365-security/configuration-analyzer-for-security-policies.md)。
