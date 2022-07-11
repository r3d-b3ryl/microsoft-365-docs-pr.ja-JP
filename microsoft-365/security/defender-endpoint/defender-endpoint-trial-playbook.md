---
title: 試用版プレイブック - Microsoft Defender for Endpoint
description: このガイドを使用して、90 日間の無料試用版を最大限に活用してください。 Defender for Endpoint が高度な脅威の防止、検出、調査、および対応にどのように役立つかを確認します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: 07/07/2022
ms.prod: m365-security
ms.technology: mde
ms.localizationpriority: medium
ms.reviewer: ''
f1.keywords: NOCSH
ms.openlocfilehash: 2b7a4d47d07fd609fb9dd424f2a8b89af2ed0b9b
ms.sourcegitcommit: 9fdb5c5b9eaf0c8a8d62b579a5fb5a5dc2d29fa9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2022
ms.locfileid: "66714802"
---
# <a name="trial-playbook-microsoft-defender-for-endpoint"></a>試用版プレイブック: Microsoft Defender for Endpoint

Microsoft Defender for Endpointプラン 2 試用版プレイブックへようこそ。

このプレイブックは、無料試用版を最大限に活用するのに役立つ簡単なガイドです。 Microsoft Defender チームのこの記事で推奨される手順を使用して、Defender for Endpoint が高度な脅威の防止、検出、調査、および対応に役立つ方法について説明します。

## <a name="what-is-defender-for-endpoint"></a>Defender for Endpoint とは

[Defender for Endpoint](microsoft-defender-endpoint.md) は、Windows に組み込まれている次のテクノロジと Microsoft の堅牢なクラウド サービスを組み合わせて使用するエンタープライズ エンドポイント セキュリティ プラットフォームです。 

- **エンドポイント動作センサー**: Windows に埋め込まれているこれらのセンサーは、オペレーティング システムからの動作信号を収集して処理し、Defender for Endpoint のプライベートで分離されたクラウド インスタンスにセンサー データを送信します。

- **クラウド セキュリティ分析**: Windows エコシステム、エンタープライズ クラウド製品 (Microsoft 365 など)、およびオンライン資産全体でビッグ データ、デバイスラーニング、および独自の Microsoft 光学を使用して、行動シグナルを分析情報、検出、および高度な脅威に対する推奨される対応に変換します。

- **脅威インテリジェンス**: Microsoft の狩人とセキュリティ チームによって生成され、パートナーから提供された脅威インテリジェンスによって強化された脅威インテリジェンスにより、Defender for Endpoint では、攻撃者のツール、手法、手順を特定し、収集されたセンサー データで監視されたときにアラートを生成できます。

<center><h2>Microsoft Defender for Endpoint</center></h2>
<table>
<tr>
<td><a href="microsoft-defender-endpoint.md#tvm"><center><img src="images/logo-mdvm.png" alt="Vulnerability Management"> <br><b>コア Defender 脆弱性の管理</b></center></a></td>
<td><a href="microsoft-defender-endpoint.md#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>攻撃面の減少</b></center></a></td>
<td><center><a href="microsoft-defender-endpoint.md#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>次世代の保護</b></a></center></td>
<td><center><a href="microsoft-defender-endpoint.md#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>エンドポイントでの検出と対応</b></a></center></td>
<td><center><a href="microsoft-defender-endpoint.md#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>調査と修復の自動化</b></a></center></td>
<td><center><a href="microsoft-defender-endpoint.md#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Microsoft 脅威エキスパート</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="microsoft-defender-endpoint.md#apis"><center><b>一元的な構成と管理、API</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="microsoft-defender-endpoint.md#mtp"><center><b>Microsoft 365 Defender</a></center></b></td>
</tr>
</table>
<br>

**では、始めましょう。**

## <a name="set-up-your-trial"></a>試用版を設定する

1. [ライセンスの状態を確認します](#step-1-confirm-your-license-state)。
2. [ロールベースのアクセス制御を設定し、セキュリティ チームにアクセス許可を付与します](#step-2-set-up-role-based-access-control-and-grant-permissions-to-your-security-team)。
3. [Microsoft 365 Defender ポータルにアクセスします](#step-3-visit-the-microsoft-365-defender-portal)。
4. [サポートされている管理ツールのいずれかを使用してエンドポイントをオンボード](#step-4-onboard-endpoints-using-any-of-the-supported-management-tools)します。
5. [機能を構成します](#step-5-configure-capabilities)。
6. [シミュレートされた攻撃を通じてMicrosoft Defender for Endpointを体験します](#step-6-experience-microsoft-defender-for-endpoint-through-simulated-attacks)。
7. [Microsoft Defender for Endpoint評価ラボを設定](#step-7-set-up-the-microsoft-defender-for-endpoint-evaluation-lab)します。

## <a name="step-1-confirm-your-license-state"></a>手順 1: ライセンスの状態を確認する

Defender for Endpoint サブスクリプションが適切にプロビジョニングされていることを確認するには、Microsoft 365 管理センター () または Azure Active Directory ([https://admin.microsoft.com](https://admin.microsoft.com)[https://portal.azure.com](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)) でライセンスの状態を確認します。

[ライセンスの状態を確認します](production-deployment.md#check-license-state)。

## <a name="step-2-set-up-role-based-access-control-and-grant-permissions-to-your-security-team"></a>手順 2: ロールベースのアクセス制御を設定し、セキュリティ チームにアクセス許可を付与する

Microsoft では、最小限の特権の概念を使用することをお勧めします。 Defender for Endpoint では、Azure Active Directory 内の組み込みロールが使用されます。 [使用可能なさまざまなロールを確認](/azure/active-directory/roles/permissions-reference) し、セキュリティ チームに適したロールを選択します。 一部のロールは、試用版の完了後に一時的に適用して削除する必要がある場合があります。

[Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure)を使用してロールを管理し、ディレクトリアクセス許可を持つユーザーに対して追加の監査、制御、アクセス レビューを提供します。

Defender for Endpoint では、アクセス許可を管理する 2 つの方法がサポートされています。

- 基本的なアクセス許可管理: アクセス許可をフル アクセスまたは読み取り専用に設定します。 Azure Active Directory のグローバル管理者ロールまたはセキュリティ管理者ロールを持つユーザーは、フル アクセス権を持ちます。 セキュリティ リーダー ロールには読み取り専用アクセス権があり、マシン/デバイス インベントリを表示するためのアクセス権は付与されません。
- ロールベースのアクセス制御 (RBAC): ロールを定義し、Azure AD ユーザー グループをロールに割り当て、ユーザー グループにデバイス グループへのアクセス権を付与することで、きめ細かなアクセス許可を設定します。 詳細については、「 [ロールベースのアクセス制御を使用したポータル アクセスの管理](rbac.md)」を参照してください。

## <a name="step-3-visit-the-microsoft-365-defender-portal"></a>手順 3: Microsoft 365 Defender ポータルにアクセスする

Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) では、Defender for Endpoint 機能にアクセスできます。

1. Microsoft 365 Defender ポータルで[想定される内容を確認](../defender/microsoft-365-defender-portal.md)します。

2. [https://security.microsoft.com](https://security.microsoft.com) に移動し、サインインします。

3. ナビゲーション ウィンドウで、[エンドポイント] セクション **を** 参照して、機能にアクセスします。 

## <a name="step-4-onboard-endpoints-using-any-of-the-supported-management-tools"></a>手順 4: サポートされている管理ツールのいずれかを使用してエンドポイントをオンボードする 

このセクションでは、デバイス (エンドポイント) をオンボードするための一般的な手順について説明します。

1. [このビデオでは](https://www.microsoft.com/videoplayer/embed/RE4bGqr) 、オンボード プロセスの概要と、使用可能なツールと方法について説明します。

2. [デバイスオンボード ツールのオプションを](onboarding.md)確認し、環境に最適なオプションを選択します。 

## <a name="step-5-configure-capabilities"></a>手順 5: 機能を構成する 

デバイス (エンドポイント) をオンボードした後、エンドポイントの検出と応答、次世代の保護、攻撃面の削減など、さまざまな機能を構成します。

[次の表](onboarding.md)を使用して、構成するコンポーネントを選択します。 使用可能なすべての機能を構成することをお勧めしますが、適用されない機能はスキップできます。

## <a name="step-6-experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>手順 6: シミュレートされた攻撃によるMicrosoft Defender for Endpointを体験する

複数のデバイスをサービスにオンボードする前に、Defender for Endpoint を体験したい場合があります。 これを行うには、いくつかのテスト デバイスで制御された攻撃シミュレーションを実行できます。 シミュレートされた攻撃を実行した後、Defender for Endpoint が悪意のあるアクティビティを表示する方法を確認し、効率的な対応を可能にする方法を調べることができます。

指定されたシミュレーションのいずれかを実行するには、少なくとも [1 台のオンボードデバイスが必要です](onboard-configure.md)。

1. チュートリアルにアクセスします。 Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のナビゲーション ウィンドウの [**エンドポイント**] で、[チュートリアル] を選択 **します**。

2. 各攻撃シナリオで提供されるチュートリアル ドキュメントをお読みください。 各ドキュメントには、攻撃シナリオに固有の OS とアプリケーションの要件と詳細な手順が含まれています。

3. [シミュレーションを実行します](attack-simulations.md)。

## <a name="step-7-set-up-the-microsoft-defender-for-endpoint-evaluation-lab"></a>手順 7: Microsoft Defender for Endpoint評価ラボを設定する   

Microsoft Defender for Endpoint評価ラボは、デバイスと環境の構成の複雑さを排除するように設計されているため、プラットフォームの機能の評価、シミュレーションの実行、防止、検出、修復機能の動作の確認に集中できます。 評価ラボの簡略化されたセットアップ エクスペリエンスを使用して、独自のテスト シナリオと事前に作成されたシミュレーションの実行に集中して、Defender for Endpoint のパフォーマンスを確認できます。

- 評価ラボ[のビデオの概要を確認](https://www.microsoft.com/videoplayer/embed/RE4qLUM)する
- [ラボの概要](evaluation-lab.md) 


## <a name="see-also"></a>関連項目

- [Defender for Endpoint の技術ドキュメント](microsoft-defender-endpoint.md)
- [Microsoft Security テクニカル コンテンツ ライブラリ](https://www.microsoft.com/security/content-library/Home/Index)
- [Defender for Endpoint デモンストレーション](https://cdx.transform.microsoft.com/experience-detail/d5eca65d-13a3-464d-9171-c24cf9dd6050)

