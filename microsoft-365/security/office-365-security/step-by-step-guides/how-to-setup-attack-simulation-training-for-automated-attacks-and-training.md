---
title: 攻撃シミュレーション トレーニング内で自動攻撃とトレーニングを設定する方法
description: 攻撃シミュレーションのトレーニングを自動化し、ターゲット ユーザーにペイロードを送信する手順。 このガイドに従って、特定の手法とペイロードを使用して自動攻撃フローを作成する方法について説明します。
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
ms.openlocfilehash: ccf4222878777789fb7f89b6382c858eaad9f0c2
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66994257"
---
# <a name="how-to-setup-automated-attacks-and-training-within-attack-simulation-training"></a>攻撃シミュレーション トレーニング内で自動攻撃とトレーニングを設定する方法

攻撃シミュレーション トレーニングを使用すると、組織で無害な攻撃シミュレーションを実行してフィッシングリスクを評価し、フィッシング攻撃を回避する方法をユーザーに教えることができます。 このガイドに従って、指定した条件が満たされたときに実行される特定の手法とペイロードを使用して自動化されたフローを構成し、組織に対するシミュレーションを開始します。

## <a name="what-youll-need"></a>必要なもの

- Microsoft Defender for Office 365プラン 2 (E5 の一部として含まれています)。
- 十分なアクセス許可 (セキュリティ管理者ロール)。
- 次の手順を実行するには、5 分から 10 分かかります。

## <a name="send-a-payload-to-target-users"></a>ターゲット ユーザーにペイロードを送信する

1. [[攻撃シミュレーション トレーニング]](https://security.microsoft.com/attacksimulator) に移動します。
1. 上部のナビゲーション バーから **[シミュレーションの自動化** ] を選択します。
1. **[オートメーションの作成]** を押します。
1. Simulation オートメーションに、関連性があり、思い出に残る名前を付けます。 *次に*、
1. ポップアップから使用する手法を選択します。 *次に*、
1. この自動化に使用する最大 20 個のペイロードを手動で選択するか、または [ランダム化] を選択します。 *次に*、
1. ペイロードとして OAuth を選択した場合は、シミュレーションで使用するときにアプリに付与する名前、ロゴ、スコープ (アクセス許可) を入力する必要があります。 *次に*、
1. 組織全体を選択してラジオ ボタンを強調表示する場合は、ペイロードでターゲットを設定するユーザーを選択します。 *次に*、
1. それ以外の場合 **は、[ユーザーの追加]** を選択し、ウィザードでユーザーを検索またはフィルター処理して、[ユーザーの追加] を押します。 *次に*、
1. 必要に応じてトレーニングをカスタマイズし、それ以外の場合は [トレーニングの割り当て] (推奨) を選択したままにします。 *次に*、
1. 必要に応じて、ユーザーがフィッシングされた場合に表示されるランディング ページをカスタマイズし、それ以外の場合は Microsoft Default のままにします。 *次に*、
1. エンド ユーザー通知を希望するかどうかを選択します。その場合は配信設定を選択し、必要に応じてカスタマイズします。 *次に*、
1. シミュレーション スケジュールでは、[ **ランダム化]** または [ **固定**] のいずれかを選択できます。推奨されるオプションは [ランダム化] です。選択したら、[ *次へ*] を選択します。
1. ランダム化または固定の選択に応じて、スケジュールの詳細は異なる場合がありますが、オートメーションの開始日と終了日を含む選択の基本設定を選択します。 *次に*、
1. **[起動の詳細]** で、一意のペイロードの使用や繰り返し違反者のターゲット設定など、必要な最終的なオプションを選択し、[*次へ*] を選択します。
1. **送信** すると、Simulation オートメーションがセットアップされます。

## <a name="learn-more"></a>さらに詳しくは

完全なガイダンスについては、[攻撃シミュレーション トレーニングのシミュレーション自動化 - Office 365 |Microsoft Docs](../../office-365-security/attack-simulation-training-simulation-automations.md)。
