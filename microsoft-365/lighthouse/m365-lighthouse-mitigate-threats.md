---
title: Microsoft Defender ウイルス対策を使用してMicrosoft 365 Lighthouseの脅威を軽減する
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: algreer
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
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、Microsoft Defender ウイルス対策による脅威の軽減について説明します。
ms.openlocfilehash: 3c600c8119ba3d4a252efcf5675ab58138a69b83
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66016682"
---
# <a name="mitigate-threats-in-microsoft-365-lighthouse-with-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策を使用してMicrosoft 365 Lighthouseの脅威を軽減する

Microsoft 365 Lighthouseでは、パートナーは、すべてのテナントにわたる脅威を調査し、軽減できます。 また、デバイスでウイルス対策スキャンを開始したり、デバイスがMicrosoft Defender ウイルス対策の最新の更新プログラムを取得していることを確認したり、ウイルス対策スキャン後に保留中のアクションを確認したりできます。 Lighthouse では、Windows 10 以降を実行しているデバイスのみがサポートされます。

## <a name="before-you-begin"></a>はじめに

- Microsoft 365 Lighthouseは、顧客テナントではなく、パートナー テナントにのみ展開されますが、お客様と顧客テナントが[、Microsoft 365 Lighthouse要件](m365-lighthouse-requirements.md)に記載されている要件を満たしていることを確認してください。

- ユーザーはMicrosoft Defender ウイルス対策を実行している必要があります (Windowsに含まれています)。 Lighthouse では、Microsoft 以外のウイルス対策ソフトウェアはサポートされていません。 詳細については、「[Microsoft Defender ウイルス対策を有効にする」](/mem/intune/user-help/turn-on-defender-windows)を参照してください。

- サインイン先のパートナー テナントのグローバル管理者である必要があります。

## <a name="investigate-active-threats"></a>アクティブな脅威を調査する

特定の脅威を調査するには:

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **脅威の管理**] を選択します。

2. [ **脅威** ] タブを選択します。

3. 脅威の一覧から、調査する脅威を選択します。

[脅威の詳細] ウィンドウには、次の情報が表示されます。

| カテゴリ                                      | Definition                                                                                                   |
|-----------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| デバイスとテナント                             | 脅威が検出されたデバイス名とテナント。 デバイス名を選択すると、追加情報が表示されます。 |
| 脅威の状態                                 | 脅威の状態。                                                                                    |
| 脅威の種類                                   | 脅威の種類。                                                                                              |
| 脅威の重大度                               | 脅威の重大度 (重大、高、中、低、不明)                                                    |
| Instances                                     | デバイスに存在するこの脅威のインスタンスの数。                                                    |
| 最初に検出されました                                | このデバイスで脅威が最初に検出されたとき。                                                           |
| ドキュメント                                 | 脅威に関する追加情報へのリンク。                                                             |
| この脅威を伴うこのテナント上の他のデバイス | 同じアクティブな脅威を持つ同じテナント内の他のデバイスの一覧。                                      |
| この脅威を持つ他のテナント                | 同じアクティブな脅威を持つ他のテナントの一覧。                                                         |

特定のデバイス上の脅威を調査するには:

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **脅威の管理**] を選択します。

2. [ **ウイルス対策の保護** ] タブを選択します。

3. 一覧からデバイスを選択します。

4. デバイスの詳細ウィンドウで、[現在の **脅威** ] タブを選択します。

Lighthouse には、デバイスで検出されたすべての脅威が表示されます。 詳細を表示するには、脅威を選択します。

## <a name="scan-for-threats-on-a-device"></a>デバイス上の脅威をスキャンする

クイック スキャンは、レジストリ キーやスタートアップ フォルダーなど、マルウェアが存在する可能性がある一般的な場所を検索します。 フル スキャンでは、デバイス全体が検索されます。 ほとんどの場合、クイック スキャンで十分であり、スケジュールされたスキャンに推奨されるオプションとなっています。

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **脅威の管理**] を選択します。

2. [ **ウイルス対策の保護** ] タブを選択します。

3. デバイスの一覧から、デバイスを選択します。

4. デバイスの詳細ウィンドウで、[ **完全スキャンの実行** ] または [ **クイック スキャンの実行**] を選択します。

また、一覧の各デバイス名の横にあるチェック ボックスをオンにして、[ **完全スキャンの実行** ] または [ **クイック スキャンの実行**] を選択して、複数のデバイスをスキャンすることもできます。

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策の更新プログラムを取得する

1 つのデバイスでMicrosoft Defender ウイルス対策を更新するには:

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **脅威の管理**] を選択します。

2. [ **ウイルス対策の保護** ] タブを選択します。

3. デバイスの一覧から、デバイスを選択します。

4. デバイスの詳細ウィンドウで、[ **ウイルス対策の更新**] を選択します。

一覧の各デバイス名の横にあるチェック ボックスをオンにし、[ **ウイルス対策の更新**] を選択すると、複数のデバイスの更新プログラムを取得できます。

新しいポリシーを作成する必要がある場合は、デバイスの詳細ウィンドウで **[ポリシーの更新** ] を選択します。 Lighthouse によってMicrosoft エンドポイント マネージャー (MEM) にリダイレクトされます。 ポリシーの作成の詳細については、「[Microsoft Intuneでのコンプライアンス ポリシーの作成](/mem/intune/protect/create-compliance-policy)」を参照してください。

## <a name="check-pending-antivirus-actions-on-a-device"></a>デバイスで保留中のウイルス対策アクションを確認する

連続するアクションがデバイスに適用されると、保留中のアクション メッセージが表示されます。 デバイスで保留中のアクションを確認するには、

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **脅威の管理**] を選択します。

2. [ **ウイルス対策の保護** ] タブを選択します。

3. デバイスの一覧から、デバイスを選択します。

4. デバイスの詳細ウィンドウで、[ **デバイス アクションの状態** ] タブを選択して、保留中のアクションを表示します。

## <a name="restart-a-device"></a>デバイスの再起動

一部の更新プログラムでは、正しくインストールするためにデバイスの再起動が必要になる場合があります。

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **脅威の管理**] を選択します。

2. [ **ウイルス対策の保護** ] タブを選択します。

3. デバイスの一覧から、デバイスを選択します。

4. デバイスの詳細ウィンドウで、[ **デバイスの再起動**] を選択します。

一覧の各デバイス名の横にあるチェック ボックスをオンにし、[デバイスの再起動] を選択して、複数の **デバイスを再起動** することもできます。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 Lighthouseの要件](m365-lighthouse-requirements.md) (記事)\
[Microsoft 365 Lighthouseの脅威管理ページの概要](m365-lighthouse-threat-management-page-overview.md) (記事)\
[Microsoft Intuneでコンプライアンス ポリシーを作成する](/mem/intune/protect/create-compliance-policy) (記事)\
[Microsoft Defender ウイルス対策を有効にする](/mem/intune/user-help/turn-on-defender-windows) (記事)\
[Microsoft セキュリティ インテリジェンス](https://www.microsoft.com/wdsi/threats) (Web ページ)
