---
title: Microsoft Defender for Business のチュートリアルとシミュレーション
description: Defender for Business の使用を始めるのに役立ついくつかのチュートリアルについて説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/24/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: c955b85001a141933227873a1f74e681f74b004b
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322941"
---
# <a name="tutorials-and-simulations-in-microsoft-defender-for-business"></a>Microsoft Defender for Business のチュートリアルとシミュレーション

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐[](https://aka.ms/mdb-preview)々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは最初の一連 [のシナリオで](#try-these-preview-scenarios)起動し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Microsoft Defender for Business のセットアップが完了したばかりの場合は、Defender for Business の動作についてどこから学ぶのか疑問に思う場合があります。 この記事では、試すプレビュー シナリオと、Defender for Business で使用できるいくつかのチュートリアルとシミュレーションについて説明します。 これらのリソースは、Defender for Business が組織でどのように機能できるのか確認するために設計されています。

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business に関する短いアンケートをご覧ください</a>。 ご意見をお寄せください。
>

## <a name="try-these-preview-scenarios"></a>これらのプレビュー シナリオを試す

次の表に、Defender for Business で試すシナリオの概要を示します。 
<br/><br/>


| シナリオ  | 説明  |
|---------|---------|
| ローカル スクリプトを使用したデバイスのオンボード <br/>(*実稼働展開用ではありません*)     | Defender for Business では、各デバイスでダウンロードして実行するスクリプトを使用して、Windows 10 デバイスと 11 台のデバイスを最大 10 台までオンボードできます。 環境内での Defender for Business の動作を評価する場合に適したスクリプトは、Azure Active Directory (Azure AD) を使用して信頼を作成し、デバイスを Microsoft Intune に登録します。 詳細については、「Defender [for Business のローカル スクリプト」を参照してください](mdb-onboard-devices.md#local-script-in-defender-for-business)。         |
| デバイスを使用したオンボード Microsoft Intune     | Defender for Endpoint を取得する前Microsoft Intuneを使用していた場合は、引き続きデバイスMicrosoft Intuneを使用できます。 macOS、iOS、Android デバイスのオンボーディングを試Microsoft Intune。 詳細については、「デバイスの登録[」を参照Microsoft Intune](/mem/intune/enrollment/device-enrollment)。        |
| セキュリティ ポリシーの編集     | Defender for Business でセキュリティ ポリシーを管理している場合は、[デバイス構成] ページを使用してポリシーを表示および編集します。 詳細については、「 [Microsoft Defender for Business のポリシーを表示または編集する」を参照してください](mdb-view-edit-policies.md)。        |
| シミュレートされた攻撃を実行する   | Defender for Business では、いくつかのチュートリアルとシミュレーションを使用できます。 これらのチュートリアルとシミュレーションは、Defender for Business の脅威保護機能が組織でどのように機能できるのか、直接説明するように設計されています。 1 つ以上のチュートリアルを試す方法については、「 [Microsoft Defender for Business の推奨チュートリアル」を参照してください](#recommended-tutorials-for-defender-for-business)。         |
| [インシデントの表示] Microsoft 365 Lighthouse     | アプリを使用[している](/partner-center/enrolling-in-the-csp-program)Microsoft クラウド ソリューション プロバイダー場合Microsoft 365 Lighthouse、顧客のテナント間のインシデントをすぐにポータルでMicrosoft 365 Lighthouseできます。 詳細については、「Microsoft Defender [for Business Microsoft 365 Lighthouse」を参照してください](mdb-lighthouse-integration.md)。       |


## <a name="recommended-tutorials-for-defender-for-business"></a>Defender for Business の推奨チュートリアル

次の表に、Defender for Business のお客様に推奨されるチュートリアルを示します。
<br/><br/>


| チュートリアル  | 説明  |
|---------|---------|
| **ドキュメントドロップバックドア**     | テスト デバイスにファイル ベースのマルウェアを導入する攻撃をシミュレートします。 このチュートリアルでは、シミュレーション ファイルを取得して使用する方法と、シミュレーション ポータルで監視するMicrosoft 365 Defenderします。 <br/><br/>このチュートリアルでは、Microsoft Wordデバイスにインストールする必要があります。   |
| **ライブ応答のチュートリアル**     | Live Response で基本コマンドと高度なコマンドを使用する方法について説明します。 不審なファイルを見つけ、ファイルを修復し、デバイス上の情報を収集する方法について学習します。   |
| **脅威&の管理 (コア シナリオ)**     | 次の 3 つの脅威と脆弱性の管理の詳細について説明します。 <br/><br/>1. 組織の脅威と脆弱性の暴露を減らします。 <br/>2. 修復を要求します。 <br/>3. セキュリティに関する推奨事項の例外を作成します。 <br/><br/> 脅威と脆弱性の管理は、エンドポイントの脆弱性と誤った構成の検出、事前設定、および修復にリスクベースのアプローチを使用します。      |

各チュートリアルには、シナリオ、動作方法、および実行方法を説明するチュートリアル ドキュメントが含まれています。

> [!TIP]
> チュートリアル ドキュメントには、Microsoft Defender for Endpoint への参照が表示されます。 この記事に記載されているチュートリアルは、Defender for Endpoint または Defender for Business で使用できます。

## <a name="how-to-access-the-tutorials"></a>チュートリアルにアクセスする方法

1. ポータル () にMicrosoft 365 Defenderサインイン[https://security.microsoft.com](https://security.microsoft.com)します。

2. ナビゲーション ウィンドウの [エンドポイント] **で、[チュートリアル**] **を選択します**。

3. 次のいずれかのチュートリアルを選択します。

   - **ドキュメントドロップバックドア**
   - **ライブ応答のチュートリアル**
   - **脅威&の管理 (コア シナリオ)**

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Business でデバイスを管理する](mdb-manage-devices.md)

- [Microsoft Defender for Business でのインシデントの表示と管理](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business での脅威への対応と軽減](mdb-respond-mitigate-threats.md)

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)