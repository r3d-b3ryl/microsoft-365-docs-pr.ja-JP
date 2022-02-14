---
title: Microsoft Defender for Business のチュートリアルとシミュレーション (プレビュー)
description: Defender for Business (プレビュー) の使用を始めるのに役立ついくつかのチュートリアルについて説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 01/06/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: ddaac75774c79ac946754cea5089507e0972fc98
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62464920"
---
# <a name="tutorials-and-simulations-in-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business のチュートリアルとシミュレーション (プレビュー)

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐[](https://aka.ms/mdb-preview)々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは最初の一連 [のシナリオで](#try-these-preview-scenarios)起動し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Microsoft Defender for Business (プレビュー) のセットアップが完了したばかりの場合は、Defender for Business (プレビュー) の動作についてどこから学ぶのか疑問に思う場合があります。 この記事では、試すプレビュー シナリオと、Defender for Business (プレビュー) で使用できるいくつかのチュートリアルとシミュレーションについて説明します。 これらのリソースは、Defender for Business (プレビュー) が組織でどのように機能するのか確認するために設計されています。

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business に関する短いアンケートをご覧ください</a>。 ご意見をお寄せください。
>

## <a name="try-these-preview-scenarios"></a>これらのプレビュー シナリオを試す

次の表に、Defender for Business (プレビュー) のプレビュー中に試すシナリオの概要を示します。 
<br/><br/>


| シナリオ  | 説明  |
|---------|---------|
| ローカル スクリプトを使用したデバイスのオンボード     | Defender for Business (プレビュー) では、各Windows 10でダウンロードして実行するスクリプトを使用して、デバイスと 11 台のデバイスをオンボードできます。 スクリプトは、ユーザー (Azure Active Directory) とのAzure ADを作成し、デバイスを Microsoft Intune。 詳細については、「Defender for Business (プレビュー)でローカル スクリプトを使用してデバイスをオンボード [する」を参照してください](mdb-onboard-devices.md#onboard-a-device-using-a-local-script-in-defender-for-business)。         |
| デバイスを使用したオンボード Microsoft Intune     | Defender for Endpoint を取得する前Microsoft Intuneを既に使用していた場合は、Microsoft Intuneデバイスをオンボードできます。 macOS、iOS、Linux、および Android デバイスのオンボーディングを試Microsoft Intune。 詳細については、「デバイスの[登録」を参照Microsoft Intune](/mem/intune/enrollment/device-enrollment)。        |
| セキュリティ ポリシーの編集     | Defender for Business (プレビュー) でセキュリティ ポリシーを管理している場合は、[デバイス構成] ページを使用してポリシーを表示および編集します。 詳細については、「Microsoft Defender for Business (プレビュー)のポリシーを表示 [または編集する」を参照してください](mdb-view-edit-policies.md)。        |
| シミュレートされた攻撃を実行する   | Defender for Business (プレビュー) では、いくつかのチュートリアルとシミュレーションを利用できます。 これらのチュートリアルとシミュレーションは、Defender for Business (プレビュー) の脅威保護機能が組織でどのように機能できるのか、直接説明するように設計されています。 1 つ以上のチュートリアルを試す方法については、「 [Microsoft Defender for Business (プレビュー)の推奨チュートリアル」を参照してください](#recommended-tutorials-for-defender-for-business)。         |
| [インシデントの表示] Microsoft 365 Lighthouse     | ユーザーが [Microsoft クラウド ソリューション プロバイダーをMicrosoft 365 Lighthouse](/partner-center/enrolling-in-the-csp-program)している場合は、顧客のテナント間のインシデントをすぐにポータルでMicrosoft 365 Lighthouseできます。 詳細については、「Microsoft 365 Lighthouse [Microsoft Defender for Business (プレビュー)」を参照してください](mdb-lighthouse-integration.md)。       |


## <a name="recommended-tutorials-for-defender-for-business"></a>Defender for Business の推奨チュートリアル

次の表に、Defender for Business (プレビュー) のお客様に推奨されるチュートリアルを示します。
<br/><br/>


| チュートリアル  | 説明  |
|---------|---------|
| **ドキュメントドロップバックドア**     | テスト デバイスにファイル ベースのマルウェアを導入する攻撃をシミュレートします。 チュートリアルでは、シミュレーション ファイルを取得して使用する方法と、シミュレーション ポータルで何を監視Microsoft 365 Defenderします。 <br/><br/>このチュートリアルでは、Microsoft Wordデバイスにインストールする必要があります。   |
| **ライブ応答のチュートリアル**     | Live Response で基本コマンドと高度なコマンドを使用する方法について説明します。 不審なファイルを見つけ、ファイルを修復し、デバイス上の情報を収集する方法について学習します。   |
| **脅威&の管理 (コア シナリオ)**     | 次の 3 つの脅威と脆弱性の管理の詳細について説明します。 <br/><br/>1. 組織の脅威と脆弱性の暴露を減らします。 <br/>2. 修復を要求します。 <br/>3. セキュリティに関する推奨事項の例外を作成します。 <br/><br/> 脅威と脆弱性の管理は、エンドポイントの脆弱性と誤った構成の検出、事前設定、および修復にリスクベースのアプローチを使用します。      |

各チュートリアルには、シナリオ、動作方法、および実行方法を説明するチュートリアル ドキュメントが含まれています。

> [!TIP]
> チュートリアル ドキュメントには、Microsoft Defender for Endpoint への参照が表示されます。 この記事に記載されているチュートリアルは、Defender for Endpoint または Defender for Business (プレビュー) で使用できます。

## <a name="how-to-access-the-tutorials"></a>チュートリアルにアクセスする方法

1. ポータル () にMicrosoft 365 Defenderサインイン[https://security.microsoft.com](https://security.microsoft.com)します。

2. ナビゲーション ウィンドウの [エンドポイント] **で、[チュートリアル**] **を選択します**。

3. 次のいずれかのチュートリアルを選択します。

   - **ドキュメントドロップバックドア**
   - **ライブ応答のチュートリアル**
   - **脅威&の管理 (コア シナリオ)**

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Business でデバイスを管理する (プレビュー)](mdb-manage-devices.md)

- [Microsoft Defender for Business でのインシデントの表示と管理 (プレビュー)](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business での脅威への対応と軽減 (プレビュー)](mdb-respond-mitigate-threats.md)

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)