---
title: 脅威を軽減するには、Microsoft Defender ウイルス対策
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 管理サービス プロバイダー (MSP) が Microsoft 365 Lighthouseを使用して脅威を軽減する方法についてMicrosoft Defender ウイルス対策。
ms.openlocfilehash: 3d7eeb54c6f11e73bca71271faa7c09b30627ec2
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2021
ms.locfileid: "61424065"
---
# <a name="mitigate-threats-with-microsoft-defender-antivirus"></a>脅威を軽減するには、Microsoft Defender ウイルス対策

> [!NOTE]
> この記事で説明する機能はプレビューで、変更される可能性があります。要件を満たすパートナーだけが [利用できます](m365-lighthouse-requirements.md)。 組織にアカウントが設定されていない場合Microsoft 365 Lighthouse[を参照してください](m365-lighthouse-sign-up.md)Microsoft 365 Lighthouse。

Microsoft 365 Lighthouseパートナーは、すべてのテナントの脅威を調査および軽減できます。 デバイスでウイルス対策スキャンを開始し、デバイスが最新の更新プログラムをMicrosoft Defender ウイルス対策、ウイルス対策スキャン後の保留中のアクションを確認することもできます。 ライトハウスでは、デバイスがWindows 10サポートされます。

## <a name="before-you-begin"></a>始める前に

- Microsoft 365 Lighthouseは、顧客テナントではなくパートナー テナントにのみ展開されますが、ユーザーと顧客テナントが Microsoft 365 Lighthouse 要件に記載されている[要件を満たしていることを確認](m365-lighthouse-requirements.md)します。

- ユーザーは、(Microsoft Defender ウイルス対策に含まれる) Windows。 ライトハウスでは、Microsoft 以外のウイルス対策ソフトウェアはサポートされていません。 詳細については、「電源を入[Microsoft Defender ウイルス対策」 を参照してください](/mem/intune/user-help/turn-on-defender-windows)。

- サインインするパートナー テナントのグローバル管理者である必要があります。

## <a name="investigate-active-threats"></a>アクティブな脅威を調査する

特定の脅威を調査するには、次の方法を実行します。

1. ライトハウスの左側のナビゲーション ウィンドウで、[脅威の管理] **を選択します**。

2. [脅威] **タブを選択** します。

3. 脅威リストから、調査する脅威を選択します。

脅威の詳細ウィンドウには、次の情報が表示されます。

| カテゴリ                                      | Definition                                                                                                   |
|-----------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| デバイスとテナント                             | 脅威が検出されたデバイス名とテナント。 デバイス名を選択すると、追加情報が表示されます。 |
| 脅威の状態                                 | 脅威の状態。                                                                                    |
| 脅威の種類                                   | 脅威の種類。                                                                                              |
| 脅威の重大度                               | 脅威の重大度 (重大、高、中、低、不明)                                                    |
| Instances                                     | デバイスに存在するこの脅威のインスタンスの数。                                                    |
| 最初に検出された                                | このデバイスで脅威が最初に検出された場合。                                                           |
| ドキュメント                                 | 脅威に関する追加情報へのリンク。                                                             |
| この脅威を持つこのテナントの他のデバイス | 同じアクティブな脅威を持つ同じテナント内の他のデバイスの一覧。                                      |
| この脅威を持つ他のテナント                | 同じアクティブな脅威を持つ他のテナントの一覧。                                                         |

特定のデバイス上の脅威を調査するには、次の方法を実行します。

1. ライトハウスの左側のナビゲーション ウィンドウで、[脅威の管理] **を選択します**。

2. [ウイルス対策 **の保護] タブを** 選択します。

3. リストからデバイスを選択します。

4. デバイスの詳細ウィンドウで、[現在の脅威 **] タブを選択** します。

ライトハウスには、デバイスで見つかったすべての脅威が表示されます。 詳細を表示するには、脅威を選択します。

## <a name="scan-for-threats-on-a-device"></a>デバイス上の脅威をスキャンする

クイック スキャンでは、レジストリ キーやスタートアップ フォルダーなど、マルウェアが発生する可能性がある一般的な場所を検索します。 フル スキャンでは、デバイス全体が検索されます。 ほとんどの場合、クイック スキャンで十分であり、スケジュールされたスキャンに推奨されるオプションです。

1. ライトハウスの左側のナビゲーション ウィンドウで、[脅威の管理] **を選択します**。

2. [ウイルス対策 **の保護] タブを** 選択します。

3. デバイスの一覧から、デバイスを選択します。

4. [デバイスの詳細] ウィンドウで、[フル スキャンの **実行] または [** クイック スキャン **の実行] を選択します**。

また、リスト内の各デバイス名の横にあるチェック ボックスをオンにして、[フル スキャンの実行] または [クイック スキャンの実行] を選択して、複数のデバイス **をスキャンすることもできます**。

## <a name="get-updates-for-microsoft-defender-antivirus"></a>ユーザーの更新プログラムを取得Microsoft Defender ウイルス対策

単一のデバイスMicrosoft Defender ウイルス対策を更新するには、次の方法を実行します。

1. ライトハウスの左側のナビゲーション ウィンドウで、[脅威の管理] **を選択します**。

2. [ウイルス対策 **の保護] タブを** 選択します。

3. デバイスの一覧から、デバイスを選択します。

4. [デバイスの詳細] ウィンドウで、[ウイルス対策の更新 **] を選択します**。

リスト内の各デバイス名の横にあるチェック ボックスをオンにして、[ウイルス対策の更新] を選択すると、複数のデバイスの更新プログラム **を取得できます**。

新しいポリシーを作成する必要がある場合は、デバイスの詳細ウィンドウ **から** [ポリシーの更新] を選択します。 ライトハウスは、ユーザーを Microsoft エンドポイント マネージャー (MEM) にリダイレクトします。 ポリシーの作成の詳細については、「コンプライアンス ポリシーを作成[する」を](/mem/intune/protect/create-compliance-policy)参照Microsoft Intune。

## <a name="check-pending-antivirus-actions-on-a-device"></a>デバイスで保留中のウイルス対策アクションを確認する

デバイスに連続したアクションが適用されると、保留中のアクション メッセージが表示されます。 デバイスで保留中のアクションを確認するには、次の操作を実行します。

1. ライトハウスの左側のナビゲーション ウィンドウで、[脅威の管理] **を選択します**。

2. [ウイルス対策 **の保護] タブを** 選択します。

3. デバイスの一覧から、デバイスを選択します。

4. [デバイスの詳細] ウィンドウで、[ **デバイスアクションの状態]** タブを選択して、保留中のアクションを表示します。

## <a name="restart-a-device"></a>デバイスの再起動

一部の更新プログラムでは、正しくインストールするためにデバイスの再起動が必要な場合があります。

1. ライトハウスの左側のナビゲーション ウィンドウで、[脅威の管理] **を選択します**。

2. [ウイルス対策 **の保護] タブを** 選択します。

3. デバイスの一覧から、デバイスを選択します。

4. [デバイスの詳細] ウィンドウで、[デバイスの再起動] **を選択します**。

リスト内の各デバイス名の横にあるチェック ボックスをオンにして、[デバイスの再起動] を選択して、複数のデバイスを **再起動することもできます**。

## <a name="related-content"></a>関連コンテンツ

[ユーザーのMicrosoft 365 Lighthouse](m365-lighthouse-requirements.md) (記事)\
[脅威管理ページの概要 ](m365-lighthouse-threat-management-page-overview.md) (記事)\
[コンプライアンス ポリシーを作成する (Microsoft Intune)\](/mem/intune/protect/create-compliance-policy)
[[設定] Microsoft Defender ウイルス対策](/mem/intune/user-help/turn-on-defender-windows)オンにする (記事)\
[Microsoft セキュリティ インテリジェンス](https://www.microsoft.com/wdsi/threats)
