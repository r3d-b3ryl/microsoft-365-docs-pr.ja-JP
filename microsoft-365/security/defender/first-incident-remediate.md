---
title: 手順 2.  最初のインシデントを修復する
description: 最初のインシデントの修復を開始する方法をMicrosoft 365 Defender。
keywords: インシデント、アラート、調査、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、メールボックス、電子メール、365、microsoft、m365、インシデント対応、サイバー攻撃
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 787fd55e9ad17607cfa0fa5f787a279bb0e2d1839d2029b9a7ec6a4bb5f1b65a
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53838970"
---
# <a name="step-2-remediate-your-first-incident"></a>手順 2. 最初のインシデントを修復する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defender検出および分析機能を提供するだけでなく、マルウェアの格納と根絶も提供します。 Containment には、攻撃の影響を軽減する手順が含まれていますが、根絶によって、攻撃者のアクティビティのすべての痕跡がネットワークから削除されます。  Microsoft 365 Defenderには、オペレーティング システムと攻撃の種類に応じて[](m365d-autoir.md)自動修復するように構成できる修復アクションがいくつか用意されています。

Microsoft 365 Defenderは、アナリストが手動で開始できるいくつかの修復アクションを提供します。 アクションは、デバイス上のアクションとファイルのアクションという 2 つのカテゴリに分けられます。 一部のアクションを使用して脅威を直ちに停止し、他のアクションはさらに法医学分析を支援します。

## <a name="actions-on-devices"></a>デバイスでのアクション

- **デバイスを分離** する - このアクティビティは、マルウェアの拡散を最小限に抑え、悪意のあるアクターが攻撃を続けることなく分析を継続するために、すべてのネットワーク トラフィック (インターネットと内部) を直ちにブロックします。 許可される唯一の接続は、Microsoft Defender for Identity サービス クラウドへの接続なので、Microsoft Defender for Identity は引き続きデバイスを監視できます。 
- **アプリの実行を** 制限する - アプリケーションの実行を制限するために、Microsoft が発行した証明書によって署名されている場合にのみファイルを実行できるコード整合性ポリシーが適用されます。 この制限方法は、攻撃者が侵害されたデバイスを制御し、さらに悪意のあるアクティビティを実行するのを防ぐのに役立ちます。
- **[ウイルス対策スキャン** の実行] - Defender ウイルスMicrosoft Defender ウイルス対策がアクティブなウイルス対策ソリューションかどうかに関Microsoft Defender ウイルス対策、他のウイルス対策ソリューションと一緒にスキャンを実行できます。 別のウイルス対策ベンダー製品がプライマリ エンドポイント保護ソリューションである場合は、パッシブ モードで Defender ウイルス対策を実行できます。
- **自動調査を開始する** - デバイスで新しい汎用自動調査を開始できます。 調査の実行中、デバイスから生成された他のアラートは、その調査が完了するまで、継続的な自動調査に追加されます。 さらに、他のデバイスで同じ脅威が見られる場合は、それらのデバイスが調査に追加されます。
- **ライブ応答の開始** - ライブ応答は、リモート シェル接続を使用してデバイスに瞬時にアクセスできる機能です。 これにより、詳細な調査作業を行い、迅速に特定された脅威をリアルタイムに含める即時対応アクションを実行できます。 ライブ応答は、法医学データの収集、スクリプトの実行、分析のための疑わしいエンティティの送信、脅威の修復、および新たな脅威の予防的な捜しを可能にすることで、調査を強化するように設計されています。
- **調査パッケージの収集** - 調査または対応プロセスの一環として、デバイスから調査パッケージを収集できます。 調査パッケージを収集することで、デバイスの現在の状態を特定し、攻撃者が使用するツールと手法をさらに理解できます。 
- **脅威の専門家** に相談する (デバイスとファイルの両方のアクションで利用可能) - 既に侵害されている可能性のあるデバイスやデバイスに関する詳細な分析情報については、Microsoft の脅威専門家に問い合うことができます。 Microsoft の脅威の専門家は、迅速かつ正確な対応のために、Microsoft Defender セキュリティ センター内から直接関与できます。 

## <a name="actions-on-files"></a>ファイルに対するアクション

- **ファイルの停止と** 検疫 - このアクションには、実行中のプロセスの停止、ファイルの検疫、レジストリ キーなどの永続的なデータの削除が含まれます。 このアクションは、過去 30 日間Windows 10バージョン 1703 以降のデバイスで有効になります。 
- **ファイルをブロックまたは許可** するインジケーターを追加する - 悪意のある可能性のあるファイルやマルウェアの疑いを禁止することで、組織内の攻撃の伝播を防止します。 この操作により、ファイルが組織内のデバイスで読み取り、書き込み、または実行されるのを防ぐ。
- **ファイルをダウンロードまたは収集** する – このアクションを使用すると、アナリストは、組織による詳細な分析のために、.zipで保護されたファイルをアーカイブ ファイルにダウンロードできます。
- **深い分析** – このアクションは、セキュリティで保護された完全にインストルメント化されたクラウド環境でファイルを実行します。 詳細な分析結果は、ファイルのアクティビティ、観察された動作、およびドロップされたファイル、レジストリの変更、IP アドレスとの通信など、関連する成果物を示します。 

「インシデントの検出、 [トリ](first-incident-analyze.md#analyze-your-first-incident)アージ、分析」の例を続けて、アナリストは次のアクションでこのインシデントを修復できます。

1. ユーザー アカウントのパスワードをすぐにリセットする
2. 詳細な分析が完了するまでMicrosoft 365 Defenderデバイスを分離する
3. 悪意のあるファイルがウイルスから検疫されたSharePoint
4. マルウェアの影響を受けたエンドポイントを確認する
5. システムの再構築
6. 他のユーザーに対Microsoft Cloud App Security同様のアラートを確認する
7. Tor IP アドレスをブロックする Microsoft Defender for Endpoint でカスタム インジケーターを作成する
8. 次の図に示Microsoft Cloud App Securityのような、この種類のアラートのガバナンス アクションを作成します。

   :::image type="content" source="../../media/first-incident-remediate/first-incident-mcas-governance.png" alt-text="ポータルでのガバナンス アクションMicrosoft Cloud App Security例"::: 
 
修復アクションの多くを、このページで適用および追跡Microsoft 365 Defender。 

## <a name="using-playbooks"></a>プレイブックの使用

さらに、プレイブックを使用して自動修復を作成することもできます。 現在、Microsoft には、[次のシナリオ](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks)GitHubプレイブックを提供する Playbook テンプレートがインストールされています。

- ユーザー検証を要求した後、機密性の高いファイル共有を削除する
- まれな国の自動トリアージアラート
- アカウントを無効にする前にマネージャーアクションを要求する
- 悪意のある受信トレイ ルールを無効にする

Playbooks は、Power Automateを使用して、特定の条件がトリガーされた後に特定のアクティビティを自動化するためのカスタムのロボット プロセスオートメーション フローを作成します。 組織は、既存のテンプレートまたはゼロからプレイブックを作成できます。 

次に例を示します。
 
:::image type="content" source="../../media/first-incident-remediate/first-incident-power-automate.png" alt-text="カスタムのロボット プロセスPower Automateフローの例"::: 
 
また、インシデント後のレビュー中に[](first-incident-post.md)プレイブックを作成して、インシデントからの修復アクションを作成して、迅速な修復アクションを実行することもできます。 

## <a name="next-step"></a>次の手順

[![手順 3: インシデントのインシデント後レビューを実行する方法について学習する](../../media/first-incident-overview/first-incident-path-step3.png)](first-incident-post.md)

インシデントのインシデント [後レビューを実行する方法について学習します](first-incident-post.md)。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの調査](investigate-incidents.md)
- [インシデントの管理](manage-incidents.md)
