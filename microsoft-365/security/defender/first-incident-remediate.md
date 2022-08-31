---
title: 手順 2.  最初のインシデントを修復する
description: Microsoft 365 Defenderでの最初のインシデントの修復を開始する方法。
keywords: インシデント, アラート, 調査, 相関関係, 攻撃, マシン, デバイス, ユーザー, ID, ID, メールボックス, 電子メール, 365, microsoft, m365, インシデント対応, サイバー攻撃
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-firstincident
- highpri
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 63c9e47f30e113a6b79e0b290d19b8fe9e9a6399
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482298"
---
# <a name="step-2-remediate-your-first-incident"></a>手順 2。 最初のインシデントを修復する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defenderは、検出と分析の機能を提供するだけでなく、マルウェアの包含と排除も提供します。 コンテインメントには、攻撃の影響を軽減する手順が含まれていますが、根絶によって、攻撃者アクティビティのすべてのトレースがネットワークから確実に削除されます。 Microsoft 365 Defenderには、影響を受けるデバイスのオペレーティング システムと攻撃の種類に応じて[自動修復](m365d-autoir.md)するように構成できる修復アクションがいくつか用意されています。

Microsoft 365 Defenderには、アナリストが手動で開始できる修復アクションがいくつか用意されています。 アクションは、デバイス上のアクションとファイル上のアクションという 2 つのカテゴリに分けられます。 一部のアクションを使用して脅威を直ちに停止し、他のアクションを使用してフォレンジック分析をさらに進めることができます。

## <a name="actions-on-devices"></a>デバイスでのアクション

- **デバイスを分離する** - このアクティビティは、マルウェアの拡散を最小限に抑え、悪意のあるアクターが攻撃を続けることなく分析を継続できるように、すべてのネットワーク トラフィック (インターネットと内部) を直ちにブロックします。 許可される唯一の接続は、Microsoft Defender for Identity サービス クラウドに対して行われるため、Microsoft Defender for Identityは引き続きデバイスを監視できます。 
- **アプリの実行を制限** する - アプリケーションの実行を制限するために、Microsoft 発行の証明書によって署名されている場合にのみファイルを実行できるようにするコード整合性ポリシーが適用されます。 この制限方法は、攻撃者が侵害されたデバイスを制御し、さらに悪意のあるアクティビティを実行するのを防ぐのに役立ちます。
- **ウイルス対策スキャンの実行** - Microsoft Defender ウイルス対策スキャンは、Defender ウイルス対策がアクティブなウイルス対策ソリューションであるかどうかに関係なく、他のウイルス対策ソリューションと共に実行できます。 別のウイルス対策ベンダー製品が主要なエンドポイント保護ソリューションである場合は、パッシブ モードで Defender ウイルス対策を実行できます。
- **自動調査を開始** する - デバイスで新しい汎用自動調査を開始できます。 調査の実行中、デバイスから生成されたその他のアラートは、その調査が完了するまで、継続的な自動調査に追加されます。 さらに、他のデバイスで同じ脅威が見られる場合は、それらのデバイスが調査に追加されます。
- **ライブ応答の開始** - ライブ応答は、リモート シェル接続を使用してデバイスに瞬時にアクセスできる機能です。 これにより、詳細な調査作業を行い、即座に対応アクションを実行して、識別された脅威をリアルタイムで迅速に封じ込めることができます。 ライブ応答は、フォレンジック データの収集、スクリプトの実行、分析のための疑わしいエンティティの送信、脅威の修復、新たな脅威の予防的な捜索を可能にすることで、調査を強化するように設計されています。
- **調査パッケージを収集** する - 調査または対応プロセスの一環として、デバイスから調査パッケージを収集できます。 調査パッケージを収集することで、デバイスの現在の状態を特定し、攻撃者が使用するツールと手法をさらに理解できます。 
- **脅威の専門家に問い合わせてください** (デバイスとファイルのアクションの両方で利用可能) - 侵害された可能性のあるデバイスまたは既に侵害されているデバイスに関する詳細な分析情報については、Microsoft の脅威の専門家に問い合わせてください。 Microsoft の脅威の専門家は、Microsoft 365 Defender内から直接関与して、タイムリーで正確な対応を行うことができます。 

## <a name="actions-on-files"></a>ファイルへのアクション

- **停止ファイルと検疫ファイル** - このアクションには、プロセスの実行の停止、ファイルの検疫、レジストリ キーなどの永続的なデータの削除が含まれます。 このアクションは、ファイルが過去 30 日間に観察されたバージョン 1703 以降のWindows 11またはWindows 10を持つデバイスで有効になります。 
- **ファイルをブロックまたは許可するインジケーターを追加** する - 悪意のある可能性のあるファイルや疑わしいマルウェアを禁止することで、組織内での攻撃の伝播を防ぎます。 この操作により、ファイルが組織内のデバイスで読み取り、書き込み、または実行されなくなります。
- **ファイルのダウンロードまたは収集** – このアクションにより、アナリストは、組織による詳細な分析のために、パスワードで保護された.zipアーカイブ ファイル内のファイルをダウンロードできます。
- **詳細な分析** – このアクションは、セキュリティで保護された完全にインストルメント化されたクラウド環境でファイルを実行します。 詳細な分析結果は、ファイルのアクティビティ、観察された動作、および関連する成果物 (ドロップされたファイル、レジストリの変更、IP アドレスとの通信など) を示します。 

インシデントの [検出、トリアージ、分析](first-incident-analyze.md#analyze-your-first-incident)の例を続けて、アナリストは次のアクションでこのインシデントを修復できます。

1. ユーザー アカウントのパスワードをすぐにリセットする
2. 詳細な分析が完了するまでMicrosoft 365 Defenderでデバイスを分離する
3. 悪意のあるファイルが SharePoint から検疫されたことを確認する
4. マルウェアの影響を受けたエンドポイントを確認する
5. システムをリビルドする
6. 他のユーザーの同様のMicrosoft Defender for Cloud Appsアラートを確認する
7. tor IP アドレスをブロックするカスタム インジケーターをMicrosoft Defender for Endpointで作成する
8. 次の図に示すように、この種類のアラートに対してMicrosoft Defender for Cloud Appsでガバナンス アクションを作成します。

   :::image type="content" source="../../media/first-incident-remediate/first-incident-mcas-governance.png" alt-text="Microsoft Defender for Cloud Apps ポータルでのガバナンス アクション" lightbox="../../media/first-incident-remediate/first-incident-mcas-governance.png":::

ほとんどの修復アクションは、Microsoft 365 Defenderで適用および追跡できます。

## <a name="using-playbooks"></a>Playbooks の使用

さらに、プレイブックを使用して自動修復を作成することもできます。 現在、Microsoft は [GitHub に Playbook テンプレートを](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks) 用意しており、次のシナリオでプレイブックを提供しています。

- ユーザー検証を要求した後に機密ファイル共有を削除する
- 頻度の低い国のアラートの自動トリアージ
- アカウントを無効にする前にマネージャー アクションを要求する
- 悪意のある受信トレイルールを無効にする

プレイブックでは、Power Automate を使用して、特定の条件がトリガーされたら、特定のアクティビティを自動化するカスタムのロボット プロセス自動化フローを作成します。 組織は、既存のテンプレートから、またはゼロからプレイブックを作成できます。 

次に例を示します。
 
:::image type="content" source="../../media/first-incident-remediate/first-incident-power-automate.png" alt-text="Power Automate のカスタム のロボット プロセス自動化フロー" lightbox="../../media/first-incident-remediate/first-incident-power-automate.png"::: 
 
また、 [インシデント後のレビュー](first-incident-post.md) 中にプレイブックを作成して、解決されたインシデントから修復アクションを作成することもできます。 

## <a name="next-step"></a>次のステップ

[インシデントのインシデント後のレビューを実行する](first-incident-post.md)方法について説明します。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの調査](investigate-incidents.md)
- [インシデントの管理](manage-incidents.md)
