---
title: 連邦情報処理規格 (FIPS) 文書140-2
description: Microsoft は、暗号化モジュールが米国連邦情報処理規格に準拠していることを認定しています。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 8288438eed0f658d8058125bc90315e9a2626c08
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44066582"
---
# <a name="federal-information-processing-standard-fips-publication-140-2"></a>連邦情報処理規格 (FIPS) 文書140-2

## <a name="fips-140-2-standard-overview"></a>FIPS 140-2 標準の概要

連邦情報処理規格 (FIPS) 文書140-2 は米国政府機関向けの標準規格で、情報技術製品の暗号化モジュールの最小セキュリティ要件を定義しています。これは、「Information テクノロジ管理の改革法1996」のセクション5131で定義されています。

[暗号化モジュール検証プログラム](https://csrc.nist.gov/Projects/cryptographic-module-validation-program)(cmvp) は米国国立標準技術局 (NIST) とサイバー・センター (サイバーセキュリティ) の共同作業 (cccs) で、暗号化モジュール規格 (つまり fips 140-2) および関連する fips 暗号化規格の*セキュリティ要件*に対する暗号化モジュールを検証します。 FIPS 140-2 のセキュリティ要件は、暗号化モジュールの設計と実装に関連する11つの分野について説明しています。 NIST Information テクノロジ研究所は、モジュール内の FIPS 承認済み暗号化アルゴリズムを検証する関連プログラムを運用します。

## <a name="microsofts-approach-to-fips-140-2-validation"></a>Microsoft の FIPS 140-2 検証に対するアプローチ

Microsoft では、140-2 の要件を満たすための積極的なコミットメントを維持しています。これは、2001で標準を開始してから、検証済みの暗号化モジュールを備えています。 Microsoft は、米国標準技術局 (NIST)[暗号化モジュール検証プログラム](https://csrc.nist.gov/Projects/cryptographic-module-validation-program)(cmvp) の下で、暗号化モジュールを検証します。 多くのクラウドサービスを含む複数の Microsoft 製品は、これらの暗号化モジュールを使用します。

Microsoft Windows 暗号化モジュールの技術情報、各モジュールのセキュリティポリシー、および CMVP 証明書の詳細については、「 [windows および Windows SERVER FIPS 140-2 のコンテンツ](https://aka.ms/AA6ehud)」を参照してください。

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

現在の CMVP FIPS 140-2 実装のガイダンスでは、クラウドサービス自体に対する FIPS 140-2 検証は実行されません。クラウドサービスプロバイダーは、クラウドサービスを構成するコンピューティング要素に対して、FIPS 140 で検証された暗号化モジュールを取得して運用することを選択できます。 コンポーネントを含む Microsoft online services (FIPS 140-2 が検証されたもの) には、他にも次のようなものがあります。

- [Azure および Azure Government](https://docs.microsoft.com/azure/azure-government/documentation-government-plan-security)
- [Dynamics 365 および Dynamics 365 Government](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-microsoft-dynamics-365)
- [Office 365、Office 365 U.S. Government、Office 365 U.S. Government Defense](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-risks-and-protections)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**"FIPS 140 の検証" と "FIPS 140 準拠" の違いは何ですか。**

"FIPS 140 (検証済み)" とは、この暗号化モジュール、またはモジュールを埋め込む製品が、FIPS 140-2 要件を満たす CMVP によって検証 ("認定済み") されたことを意味します。 "FIPS 140 準拠" は、暗号化機能のために FIPS 140 検証済み製品を利用する IT 製品の業界用語です。

**Microsoft は、FIPS 140 の検証を行いますか?**

モジュールの検証を開始するためのリズムは、Windows 10 および Windows Server の機能の更新プログラムに沿っています。 ソフトウェア業界が進化すると、毎月のソフトウェア更新プログラムを使用して、オペレーティングシステムがより頻繁にリリースされます。 Microsoft undertakes では、リリース間での機能のリリースに関して、暗号化モジュールへの変更を最小限にするための検証を行います。

**FIPS 140 検証に含まれているコンピューター**

Microsoft は、Windows 10 および Windows Server を実行しているハードウェア構成の代表的なサンプルの暗号化モジュールを検証します。 一般的には、環境でハードウェアを使用しているときに、検証プロセスに使用されるサンプルに似た、この FIPS 140-2 検証を適用します。

**NIST web サイトには多数のモジュールがリストされています。エージェンシーに適用されているものをどのようにして確認できますか?**

FIPS 140-2 で検証された暗号化モジュールを使用する必要がある場合は、使用するバージョンが検証リストに表示されることを確認する必要があります。 CMVP と Microsoft は、製品リリースごとに編成された検証済みの暗号化モジュールのリストを、Windows システムにインストールされているモジュールを識別するための指示とともに保持しています。 準拠するようにシステムを構成する方法の詳細については、「 [windows および Windows SERVER FIPS 140-2 のコンテンツ](https://aka.ms/AA6ehud)」を参照してください。

**証明書での "FIPS モードでの操作" の意味**

この注意事項は、必要な構成およびセキュリティルールが、FIPS 140-2 セキュリティポリシーと一貫性のある方法で暗号化モジュールを使用するために従う必要があることを読者に通知します。 各モジュールには独自のセキュリティポリシーがあります。これにより、それが動作するセキュリティルールが正確に規定され、承認済みの暗号化アルゴリズム、暗号化キーの管理、および認証方法が採用されます。 セキュリティルールは、各モジュールのセキュリティポリシーで定義されています。 CMVP によって検証された各モジュールのセキュリティポリシーへのリンクを含む詳細については、「 [windows および Windows SERVER FIPS 140-2 のコンテンツ](https://aka.ms/AA6ehud)」を参照してください。

**FedRAMP は FIPS 140-2 の検証を必要としますか?**

はい。連邦リスク/承認管理プログラム (FedRAMP) は、FIPS 検証済み[の暗号化また](https://nvd.nist.gov/800-53/Rev4/control/SC-13)は NSA で承認された暗号化を使用することを前提とした、 [NIST SP 800-53 リビジョン 4](https://nvd.nist.gov/800-53/Rev4/)で定義されている制御基準に依存します。

**Microsoft Azure は FIPS 140-2 をどのようにサポートしていますか?**

Azure は、ハードウェア、市販のオペレーティングシステム (Linux と Windows)、および Azure 固有のバージョンの Windows を組み合わせて構築されています。 Microsoft[セキュリティ開発ライフサイクル](https://www.microsoft.com/securityengineering/sdl/)(SDL) では、オペレーティングシステムでは、ハイパースケールクラウドでの運用中に fips 140-2 の承認済みアルゴリズムを使用しているため、すべての Azure サービスがデータセキュリティに対して fips 140-2 の承認済みアルゴリズムを使用しています。

**代理店の認定プロセスで、Microsoft の FIPS 140-2 への準拠を使用できますか?**

FIPS 140-2 に準拠するには、fips 承認モードで実行するようにシステムを構成する必要があります。これには、暗号化モジュールが FIPS 承認のアルゴリズムのみを使用していることを確認することが含まれます。 準拠するようにシステムを構成する方法の詳細については、「 [windows および Windows SERVER FIPS 140-2 のコンテンツ](https://aka.ms/AA6ehud)」を参照してください。

**FIPS 140-2 と共通の基準との関係について**

これらの2つの個別のセキュリティ標準は異なりますが、相補的な目的があります。 FIPS 140-2 は、ソフトウェアおよびハードウェアの暗号化モジュールを検証することを目的として設計されていますが、共通の条件は IT ソフトウェアおよびハードウェア製品のセキュリティ機能を評価するために設計されています。 一般的な基準の評価は、多くの場合、FIPS 140-2 検証に依存して、基本的な暗号化機能が適切に実装されることを保証します。

## <a name="resources"></a>リソース

- [暗号化モジュールの FIPS Pub 140-2 セキュリティ要件](https://csrc.nist.gov/publications/fips/fips140-2/fips1402.pdf)
- [NIST 暗号化モジュール検証プログラム](https://csrc.nist.gov/groups/STM/cmvp/index.html)
- [Windows、Windows Server、および FIPS 140-2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation)
- [Microsoft Trust Center のコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)
