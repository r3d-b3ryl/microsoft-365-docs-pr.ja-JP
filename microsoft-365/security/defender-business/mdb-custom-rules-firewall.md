---
title: Microsoft Defender for Business でファイアウォール ポリシーのカスタム ルールを管理する
description: カスタム ルールは、ファイアウォール ポリシーに例外を提供します。 カスタム ルールを使用して、Microsoft Defender for Business の特定の接続をブロックまたは許可できます。
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
ms.openlocfilehash: 7df23c9f823f5c3c0435743f7a05cf4421704b32
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329797"
---
# <a name="manage-your-custom-rules-for-firewall-policies-in-microsoft-defender-for-business"></a>Microsoft Defender for Business でファイアウォール ポリシーのカスタム ルールを管理する

> [!IMPORTANT]
> Microsoft Defender for Business は、2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。 スタンドアロン サブスクリプションとしての Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐 [々にロールアウト](https://aka.ms/mdb-preview) されます。 プレビューには最初 [の一連のシナリオが含まれています](mdb-tutorials.md#try-these-preview-scenarios)。定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 


Microsoft Defender for Business には、望ましくないネットワーク トラフィックからデバイスを保護するためのファイアウォール ポリシーが含まれています。 カスタム ルールを使用して、ファイアウォール ポリシーの例外を定義できます。 つまり、カスタム ルールを使用して、特定の接続をブロックまたは許可できます。

ファイアウォール ポリシーと設定の詳細については、「 [Microsoft Defender for Business のファイアウォール」を参照してください](mdb-firewall.md)。

**この記事では、次の方法について説明します**。

- [ファイアウォール ポリシーのカスタム ルールを作成する](#create-a-custom-rule-for-a-firewall-policy)
- [ファイアウォール ポリシーのカスタム ルールを編集する](#edit-a-custom-rule-for-a-firewall-policy)
- [カスタム ルールの削除](#delete-a-custom-rule)

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business に関する短いアンケートをご覧ください</a>。 ご意見をお寄せください。
>

## <a name="create-a-custom-rule-for-a-firewall-policy"></a>ファイアウォール ポリシーのカスタム ルールを作成する

1. ポータル () にMicrosoft 365 Defenderサインイン[https://security.microsoft.com](https://security.microsoft.com)します。

2. [**EndpointsDevice** >  **構成] に移動** し、ポリシーの一覧を確認します。

3. [ファイアウォール **] セクション** で、既存のポリシーを選択するか、新しいポリシーを追加します。

4. [構成設定 **] ステップで** 、設定を確認します。 ドメイン ネットワーク、パブリック ネットワーク、 **プライベート ネットワークに** 必要 **な** 変更 **を加えます**。

5. カスタム ルールを作成するには、次の手順を実行します。 

   1. [カスタム **ルール] で**、[+ **ルールの追加] を選択します**。 (最大 150 のカスタム ルールを使用できます)。
   2. [新 **しいルールの作成] フライ** アウトで、ルールの名前と説明を指定します。
   3. プロファイルを選択します。 (オプションには、**ドメイン ネットワーク、****パブリック ネットワーク**、**またはプライベート ネットワークが含** まれます)。
   4. [リモート アドレス **の種類] ボックスの** 一覧で **、[IP] または [アプリケーション ファイル の****パス] を選択します**。
   5. [値 **] ボックス** で、適切な値を指定します。 手順 6d で選択した内容に応じて、IP アドレス、IP アドレス範囲、またはアプリケーション ファイル パスを指定できます。 (「 [ファイアウォールの設定」を参照](mdb-firewall.md)してください)。
   6. [新しい **ルールの作成] フライ** アウトで、[ルールの作成] **を選択します**。 

6. [構成設定 **] 画面で、[** 次へ] を **選択します**。

7. [ポリシー **の確認] 画面で** 、ファイアウォール ポリシー設定に加えた変更を確認します。 必要な変更を加え、[ポリシーの作成] **を選択します**。

## <a name="edit-a-custom-rule-for-a-firewall-policy"></a>ファイアウォール ポリシーのカスタム ルールを編集する

1. ポータル () にMicrosoft 365 Defenderサインイン[https://security.microsoft.com](https://security.microsoft.com)します。

2. [**EndpointsDevice** >  **構成] に移動** し、ポリシーの一覧を確認します。

3. [ファイアウォール **] セクション** で、既存のポリシーを選択するか、新しいポリシーを追加します。

4. [ **カスタム ルール] で**、ルールの一覧を確認します。

5. ルールを選択し、[編集] を **選択します**。 そのフライアウトが開きます。

6. カスタム ルールを編集するには、次の手順を実行します。

   1. [ルール **の編集] フライ** アウトで、ルールの名前と説明を確認して編集します。
   2. ルールのプロファイルを確認し、必要に応じて編集します。 (オプションには、**ドメイン ネットワーク、****パブリック ネットワーク**、**またはプライベート ネットワークが含** まれます)。
   3. [リモート アドレス **の種類] ボックスの** 一覧で **、[IP] または [アプリケーション ファイル の****パス] を選択します**。
   4. [値 **] ボックス** で、適切な値を指定します。 手順 6c で選択した内容に応じて、IP アドレス、IP アドレス範囲、またはアプリケーション ファイル パスを指定できます。 (「 [ファイアウォールの設定」を参照](mdb-firewall.md)してください)。
   5. ルール **をアクティブにするには、[****ルールを有効** にする] を [オン] に設定します。 または、ルールを無効にするには、スイッチを [オフ] に **設定します**。
   6. [ルールの **編集] フライアウト** で、[ルールの更新 **] を選択します**。 

7. [構成設定 **] 画面で、[** 次へ] を **選択します**。

8. [ポリシー **の確認] 画面で** 、ファイアウォール ポリシー設定に加えた変更を確認します。 必要な変更を加え、[ポリシーの作成] **を選択します**。

## <a name="delete-a-custom-rule"></a>カスタム ルールの削除

1. ポータル () にMicrosoft 365 Defenderサインイン[https://security.microsoft.com](https://security.microsoft.com)します。

2. [**EndpointsDevice** >  **構成] に移動** し、ポリシーの一覧を確認します。

3. [ファイアウォール **] セクション** で、既存のポリシーを選択するか、新しいポリシーを追加します。

4. [ **カスタム ルール] で**、ルールの一覧を確認します。

5. ルールを選択し、[削除] を **選択します**。 そのフライアウトが開きます。

6. 確認画面で、[削除] を **選択します**。 

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Business でのインシデントの表示と管理](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business での脅威への対応と軽減](mdb-respond-mitigate-threats.md)

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)