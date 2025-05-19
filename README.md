# Compound-Semiconductor
// SPDX-License-Identifier: MIT
pragma solidity =0.8.19;


//Registration of all actors and stakeholders
contract Registration{
    
    address Global_Regulatory_Authority;   //0x5B38Da6a701c568545dCfcB03FcB875f56beddC4 
    
    
    mapping(address=>bool) Raw_Materials_Supplier; // 0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2
    mapping(address=>bool) RnD_Department; // 0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db
    mapping(address=>bool) Wafer_Producer; //0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB
    mapping(address=>bool) Chip_Designer; // 0x617F2E2fD72FD9D5503197092aC168c91465E7f2
    mapping(address=>bool) Chip_Manufacturer; //0x17F6AD8Ef982297579C203069C1DbfFE4348c372
    mapping(address=>bool) Chip_Tester; //0x5c6B0f7Bf3E7ce046039Bd8FABdfD3f9F5021678
    mapping(address=>bool) Designated_National_Authority_1; //0x03C6FcED478cBbC9a4FAB34eF9f40767739D1Ff7
    mapping(address=>bool) Designated_National_Authority_2; //0x1aE0EA34a72D944a8C7603FfB3eC30a6669E454C
    mapping(address=>bool) Designated_National_Authority_3; //0x0A098Eda01Ce92ff4A4CCb7A4fFFb5A43EBC70DC
    mapping(address=>bool) Designated_National_Authority_4; //0xCA35b7d915458EF540aDe6068dFe2F44E8fa733c
    mapping(address=>bool) Designated_National_Authority_5; //0x14723A09ACff6D2A60DcdF7aA4AFf308FDDC160C
    mapping(address=>bool) Designated_National_Authority_6; //0x4B0897b0513fdC7C541B6d9D7E929C4e5364D2dB
    mapping(address=>bool) Data_Processing_Oracle; //0x583031D1113aD414F02576BD6afaBfb302140225
    mapping(address=>bool) Time_Series_Analysis_Oracle; //0x1c663478Cf81c16f0e3b707E6360E23Fc0F8f1F4
    mapping(address=>bool) Emission_Index_Oracle; //0xdD870fA1b7C4700F2BD7f44238821C26f7392148
      
       
    
    modifier onlyGlobal_Regulatory_Authority{
      require(msg.sender == Global_Regulatory_Authority,
      "Sender not authorized."
      );
      _;
    }   
    
    constructor() {
        Global_Regulatory_Authority=msg.sender;
    }
    
    function RegisterRaw_Materials_Supplier(address s) public onlyGlobal_Regulatory_Authority{
        require(!Raw_Materials_Supplier[s],
        "Raw_Materials_Supplier exists already"
        );
        
        Raw_Materials_Supplier[s]=true;
    }
    
    function RegisterRnD_Department(address r) public onlyGlobal_Regulatory_Authority{
        require(!RnD_Department[r],
        "R&D Department exists already"
        );
        
        RnD_Department[r]=true;
    }
    
    function RegisterWafer_Producer(address p) public onlyGlobal_Regulatory_Authority{
        require(!Wafer_Producer[p],
        "Wafer_Producer exists already"
        );
        
        Wafer_Producer[p]=true;
    }
    
    function RegisterChip_Designer(address d) public onlyGlobal_Regulatory_Authority{
        require(!Chip_Designer[d],
        "Chip_Designer exists already"
        );
        
        Chip_Designer[d]=true;
    }

    function RegisterChip_Manufacturer(address m) public onlyGlobal_Regulatory_Authority{
        require(!Chip_Manufacturer[m],
        "Chip_Manufacturer exists already"
        );
        
        Chip_Manufacturer[m]=true;
    }

    function RegisterChip_Tester(address t) public onlyGlobal_Regulatory_Authority{
        require(!Chip_Tester[t],
        "Chip_Tester exists already"
        );
        
        Chip_Tester[t]=true;
    }

     function RegisterDesignated_National_Authority_1(address d1) public onlyGlobal_Regulatory_Authority{
        require(!Designated_National_Authority_1[d1],
        "Designated_National_Authority 1 exists already"
        );
        
        Designated_National_Authority_1[d1]=true;
    }

    function RegisterDesignated_National_Authority_2(address d2) public onlyGlobal_Regulatory_Authority{
        require(!Designated_National_Authority_2[d2],
        "Designated_National_Authority 2 exists already"
        );
        
        Designated_National_Authority_2[d2]=true;
    }
    function RegisterDesignated_National_Authority_3(address d3) public onlyGlobal_Regulatory_Authority{
        require(!Designated_National_Authority_3[d3],
        "Designated_National_Authority 3 exists already"
        );
        
        Designated_National_Authority_3[d3]=true;
    }
    function RegisterDesignated_National_Authority_4(address d4) public onlyGlobal_Regulatory_Authority{
        require(!Designated_National_Authority_4[d4],
        "Designated_National_Authority 4 exists already"
        );
        
        Designated_National_Authority_4[d4]=true;
    }
    function RegisterDesignated_National_Authority_5(address d5) public onlyGlobal_Regulatory_Authority{
        require(!Designated_National_Authority_5[d5],
        "Designated_National_Authority 5 exists already"
        );
        
        Designated_National_Authority_5[d5]=true;
    }
    function RegisterDesignated_National_Authority_6(address d6) public onlyGlobal_Regulatory_Authority{
        require(!Designated_National_Authority_6[d6],
        "Designated_National_Authority 6 exists already"
        );
        
        Designated_National_Authority_6[d6]=true;
    }

    function RegisterData_Processing_Oracle(address o1) public onlyGlobal_Regulatory_Authority{
        require(!Data_Processing_Oracle[o1],
        "Data_Processing_Oracle exists already"
        );
        
        Data_Processing_Oracle[o1]=true;
    }

    function RegisterTime_Series_Analysis_Oracle(address o2) public onlyGlobal_Regulatory_Authority{
        require(!Time_Series_Analysis_Oracle[o2],
        "Time_Series_Analysis_Oracle exists already"
        );
        
        Time_Series_Analysis_Oracle[o2]=true;
    }

    function RegisterEmission_Index_Oracle(address o3) public onlyGlobal_Regulatory_Authority{
        require(!Emission_Index_Oracle[o3],
        "Emission_Index_Oracle exists already"
        );
        
        Emission_Index_Oracle[o3]=true;
    }


    
    function isGlobal_Regulatory_Authority(address g) public view returns(bool){
        return (Global_Regulatory_Authority==g);
    }
    
    function Raw_Materials_SupplierExists(address s) public view returns(bool){
        return Raw_Materials_Supplier[s];
    }

    function RnD_DepartmentExists(address r) public view returns(bool){
        return RnD_Department[r];
    }
    
    function Wafer_ProducerExists(address p) public view returns(bool){
        return Wafer_Producer[p];
    }
    
    function Chip_DesignerExists(address d) public view returns(bool){
        return Chip_Designer[d];
    }
    
    function Chip_ManufacturerExists(address m) public view returns(bool){
        return Chip_Manufacturer[m];
    }

    function Chip_TesterExists(address t) public view returns(bool){
        return Chip_Tester[t];
    }

    function Designated_National_Authority_1Exists(address d1) public view returns(bool){
        return Designated_National_Authority_1[d1];
    }

    function Designated_National_Authority_2Exists(address d2) public view returns(bool){
        return Designated_National_Authority_2[d2];
    }

    function Designated_National_Authority_3Exists(address d3) public view returns(bool){
        return Designated_National_Authority_3[d3];
    }

    function Designated_National_Authority_4Exists(address d4) public view returns(bool){
        return Designated_National_Authority_4[d4];
    }

    function Designated_National_Authority_5Exists(address d5) public view returns(bool){
        return Designated_National_Authority_5[d5];
    }

    function Designated_National_Authority_6Exists(address d6) public view returns(bool){
        return Designated_National_Authority_6[d6];
    }

    function Data_Processing_OracleExists(address o1) public view returns(bool){
        return Data_Processing_Oracle[o1];
    }

    function Time_Series_Analysis_OracleExists(address o2) public view returns(bool){
        return Time_Series_Analysis_Oracle[o2];
    }

    function Emission_Index_OracleExists(address o3) public view returns(bool){
        return Emission_Index_Oracle[o3];
    }
    
}

contract Traceability{

address payable Raw_Materials_Supplier;
    
    Registration RegistrationContract;
    uint Supplier_Carbon_Emissions_per_KG;
    uint Total_Supplier_Emissions;
    uint RnD_Carbon_Emissions_per_KG;
    uint Total_RnD_Emissions;
    uint Wafer_Production_Carbon_Emissions_per_KG;
    uint Total_Wafer_Production_Emissions;
    uint Chip_Design_Carbon_Emissions_per_KG;
    uint Total_Chip_Design_Emissions;
    uint Chip_Manufacturing_Carbon_Emissions_per_KG;
    uint Total_Chip_Manufacturing_Emissions;
    uint Chip_Testing_Carbon_Emissions_per_KG;
    uint Total_Chip_Testing_Emissions;


    constructor(address registration) {
        RegistrationContract=Registration(registration);
        
        if(!RegistrationContract.Raw_Materials_SupplierExists(msg.sender))
            revert("Sender not authorized");
    
}

    modifier onlySupplier{
    require(RegistrationContract.Raw_Materials_SupplierExists(msg.sender),
    "Sender not authorized."
    );
    _;
    } 
    modifier onlyRnD{
        require(RegistrationContract.RnD_DepartmentExists(msg.sender),
        "Sender not authorized");
        _;
    }
        modifier onlyWaferProducer{
        require(RegistrationContract.Wafer_ProducerExists(msg.sender),
        "Sender not authorized");
        _;
    }
        modifier onlyChipDesigner{
        require(RegistrationContract.Chip_DesignerExists(msg.sender),
        "Sender not authorized");
        _;
    }
        modifier onlyChipManufacturer{
        require(RegistrationContract.Chip_ManufacturerExists(msg.sender),
        "Sender not authorized");
        _;
    }
        modifier onlyChipTester{
        require(RegistrationContract.Chip_TesterExists(msg.sender),
        "Sender not authorized");
        _;
    }
        modifier onlyDesignated_National_Authority_1{
        require(RegistrationContract.Designated_National_Authority_1Exists(msg.sender),
        "Sender not authorized");
        _;
    }

        modifier onlyDesignated_National_Authority_2{
        require(RegistrationContract.Designated_National_Authority_2Exists(msg.sender),
        "Sender not authorized");
        _;
    }

        modifier onlyDesignated_National_Authority_3{
        require(RegistrationContract.Designated_National_Authority_3Exists(msg.sender),
        "Sender not authorized");
        _;
    }

        modifier onlyDesignated_National_Authority_4{
        require(RegistrationContract.Designated_National_Authority_4Exists(msg.sender),
        "Sender not authorized");
        _;
    }
        modifier onlyDesignated_National_Authority_5{
        require(RegistrationContract.Designated_National_Authority_5Exists(msg.sender),
        "Sender not authorized");
        _;
    }
        modifier onlyDesignated_National_Authority_6{
        require(RegistrationContract.Designated_National_Authority_6Exists(msg.sender),
        "Sender not authorized");
        _;
    }

    //Raw materials details
    event RawMaterialsSupplierDetailsUpdated(string SemiConductor_Metal_Name, string  Supply_chain_process_name_1, string  Supply_chain_process_name_2,
    string  Supply_chain_process_name_3, uint Supplier_Carbon_Emissions_per_KG, uint Total_raw_materials_produced_in_Kg, string  Country_of_Origin, uint Total_Supplier_Emissions);
    function UpdateRawMaterialsSupplierDetails (string memory SemiConductor_Metal_Name, string memory Supply_chain_process_name_1, string memory Supply_chain_process_name_2,
    string memory Supply_chain_process_name_3, uint Co2_emissions_Supply_chain_process_1, uint Co2_emissions_Supply_chain_process_2, 
    uint Co2_emissions_Supply_chain_process_3, uint Total_raw_materials_produced_in_Kg, string memory Country_of_Origin) public onlySupplier{

        Supplier_Carbon_Emissions_per_KG = Co2_emissions_Supply_chain_process_1 + Co2_emissions_Supply_chain_process_2 + Co2_emissions_Supply_chain_process_3;
        Total_Supplier_Emissions =  Supplier_Carbon_Emissions_per_KG * Total_raw_materials_produced_in_Kg;

        emit RawMaterialsSupplierDetailsUpdated (SemiConductor_Metal_Name,   Supply_chain_process_name_1,   Supply_chain_process_name_2,
      Supply_chain_process_name_3,  Supplier_Carbon_Emissions_per_KG,  Total_raw_materials_produced_in_Kg,   Country_of_Origin,  Total_Supplier_Emissions);
    }

    //RnD details
     event RnDDetailsUpdated(string SemiConductor_Metal_Name, string  RnD_process_name_1, string  RnD_process_name_2,
    string  RnD_process_name_3, uint RnD_Carbon_Emissions_per_KG, uint Total_materials_RnD_in_Kg, string  Country_of_Origin, uint Total_RnD_Emissions);
    function UpdateRnDDetails (string memory SemiConductor_Metal_Name, string memory RnD_process_name_1, string memory RnD_process_name_2,
    string memory RnD_process_name_3, uint Co2_emissions_RnD_process_1, uint Co2_emissions_RnD_process_2, uint Co2_emissions_RnD_process_3,
     uint Total_materials_RnD_in_Kg, string memory Country_of_Origin) public onlyRnD{

        RnD_Carbon_Emissions_per_KG= Co2_emissions_RnD_process_1 + Co2_emissions_RnD_process_2 + Co2_emissions_RnD_process_3;
        Total_RnD_Emissions =  RnD_Carbon_Emissions_per_KG * Total_materials_RnD_in_Kg;

        emit RnDDetailsUpdated (SemiConductor_Metal_Name,   RnD_process_name_1,   RnD_process_name_2,
      RnD_process_name_3,  RnD_Carbon_Emissions_per_KG,  Total_materials_RnD_in_Kg,   Country_of_Origin,  Total_RnD_Emissions);
    }

    //Wafer Production Details

    event WaferProductionDetailsUpdated(string Wafer_Metal_Name, string  Wafer_production_process_name_1, string  Wafer_production_process_name_2,
    string  Wafer_production_process_name_3, uint Wafer_Production_Carbon_Emissions_per_KG, uint Total_Wafer_Produced_in_Kg, string  Country_of_Origin, uint Total_Wafer_Production_Emissions);
    function UpdateWaferProductionDetails (string memory Wafer_Metal_Name, string memory Wafer_production_process_name_1, string memory Wafer_production_process_name_2,
    string memory Wafer_production_process_name_3, uint Co2_emissions_Wafer_Production_process_1, uint Co2_emissions_Wafer_Production_process_2, uint Co2_emissions_Wafer_Production_process_3,
      uint Total_Wafer_Production_in_Kg, string memory Country_of_Origin) public onlyWaferProducer{

        Wafer_Production_Carbon_Emissions_per_KG= Co2_emissions_Wafer_Production_process_1 + Co2_emissions_Wafer_Production_process_2 + Co2_emissions_Wafer_Production_process_3;
        Total_Wafer_Production_Emissions =  Wafer_Production_Carbon_Emissions_per_KG * Total_Wafer_Production_in_Kg;

        emit WaferProductionDetailsUpdated (Wafer_Metal_Name,   Wafer_production_process_name_1,   Wafer_production_process_name_2,
      Wafer_production_process_name_3,  RnD_Carbon_Emissions_per_KG,  Total_Wafer_Production_in_Kg,   Country_of_Origin,  Total_Wafer_Production_Emissions);
    }

    //Chip Design
    event ChipDesignDetailsUpdated(string Chip_Metal_Name, string  Chip_design_process_name_1, string  Chip_design_process_name_2,
    string  Chip_design_process_name_3, uint Chip_Design_Carbon_Emissions_per_KG, uint Total_Chips_Designed_in_Kg, string  Country_of_Origin, uint Total_Chip_Design_Emissions);
    function UpdateChipDesignDetails (string memory Chip_Metal_Name, string memory Chip_design_process_name_1, string memory Chip_design_process_name_2,
    string memory Chip_design_process_name_3, uint Co2_emissions_Chip_Design_process_1, uint Co2_emissions_Chip_Design_process_2, uint Co2_emissions_Chip_Design_process_3,
     uint Total_Chips_Designed_in_Kg, string memory Country_of_Origin) public onlyChipDesigner{

       Chip_Design_Carbon_Emissions_per_KG= Co2_emissions_Chip_Design_process_1 + Co2_emissions_Chip_Design_process_2 + Co2_emissions_Chip_Design_process_3;
        Total_Chip_Design_Emissions =  Chip_Design_Carbon_Emissions_per_KG * Total_Chips_Designed_in_Kg;

        emit ChipDesignDetailsUpdated (Chip_Metal_Name,  Chip_design_process_name_1,   Chip_design_process_name_2,
      Chip_design_process_name_3,  Chip_Design_Carbon_Emissions_per_KG,  Total_Chips_Designed_in_Kg,   Country_of_Origin,  Total_Chip_Design_Emissions);
    }

    //Chip Manufacturer
    event ChipManufacturingDetailsUpdated(string Chip_Metal_Name, string  Chip_Manufacturing_process_name_1, string  Chip_Manufacturing_process_name_2,
    string  Chip_Manufacturing_process_name_3, uint Chip_Manufacturing_Carbon_Emissions_per_KG, uint Total_Chips_Manufacturing_in_Kg, string  Country_of_Origin, uint Total_Chip_Manufacturing_Emissions);
    function UpdateChipManufacturingDetails (string memory Chip_Metal_Name, string memory Chip_Manufacturing_process_name_1, string memory Chip_Manufacturing_process_name_2,
    string memory Chip_Manufacturing_process_name_3, uint Co2_emissions_Chip_Manufacturing_process_1, uint Co2_emissions_Chip_Manufacturing_process_2, uint Co2_emissions_Chip_Manufacturing_process_3,
     uint Total_Chips_Manufactured_in_Kg, string memory Country_of_Origin) public onlyChipManufacturer{

       Chip_Manufacturing_Carbon_Emissions_per_KG= Co2_emissions_Chip_Manufacturing_process_1 + Co2_emissions_Chip_Manufacturing_process_2 + Co2_emissions_Chip_Manufacturing_process_3;
        Total_Chip_Manufacturing_Emissions =  Chip_Design_Carbon_Emissions_per_KG * Total_Chips_Manufactured_in_Kg;

        emit ChipManufacturingDetailsUpdated (Chip_Metal_Name,  Chip_Manufacturing_process_name_1,   Chip_Manufacturing_process_name_2,
      Chip_Manufacturing_process_name_3,  Chip_Design_Carbon_Emissions_per_KG,  Total_Chips_Manufactured_in_Kg,   Country_of_Origin,  Total_Chip_Manufacturing_Emissions);
    }

    //Chip Testing
    event ChipTestingDetailsUpdated(string Chip_Metal_Name, string  Chip_Testing_process_name_1, string  Chip_Testing_process_name_2,
    string  Chip_Testing_process_name_3, uint Chip_Testing_Carbon_Emissions_per_KG, uint Total_Chips_Testing_in_Kg, string  Country_of_Origin, uint Total_Chip_Testing_Emissions);
    function UpdateChipTestingDetails (string memory Chip_Metal_Name, string memory Chip_Testing_process_name_1, string memory Chip_Testing_process_name_2,
    string memory Chip_Testing_process_name_3, uint Co2_emissions_Chip_Testing_process_1, uint Co2_emissions_Chip_Testing_process_2, uint Co2_emissions_Chip_Testing_process_3,
     uint Total_Chips_Tested_in_Kg, string memory Country_of_Origin) public onlyChipTester{

       Chip_Testing_Carbon_Emissions_per_KG= Co2_emissions_Chip_Testing_process_1 + Co2_emissions_Chip_Testing_process_2 + Co2_emissions_Chip_Testing_process_3;
        Total_Chip_Testing_Emissions =  Chip_Testing_Carbon_Emissions_per_KG * Total_Chips_Tested_in_Kg;

        emit ChipTestingDetailsUpdated (Chip_Metal_Name,  Chip_Testing_process_name_1,   Chip_Testing_process_name_2,
      Chip_Testing_process_name_3,  Chip_Testing_Carbon_Emissions_per_KG,  Total_Chips_Tested_in_Kg,   Country_of_Origin,  Total_Chip_Testing_Emissions);
    }

    event Country_1EmissionsUpdated(address SupplRaw_materials_Supplier, string Country_of_Origin, uint Total_Co2_intensity);
    function updateCountry_1_Co2_Emissions (address Raw_materials_Supplier, string memory Country_of_Origin, uint Total_Co2_intensity) external onlyDesignated_National_Authority_1{

        emit Country_1EmissionsUpdated(Raw_materials_Supplier,  Country_of_Origin,  Total_Co2_intensity);
    }

    event Country_2EmissionsUpdated(address RnD_Department, string Country_of_Origin, uint Total_Co2_intensity);
    function updateCountry_2_Co2_Emissions (address RnD_Department, string memory Country_of_Origin, uint Total_Co2_intensity) external onlyDesignated_National_Authority_2{

        emit Country_2EmissionsUpdated(RnD_Department,  Country_of_Origin,  Total_Co2_intensity);
    }

    event Country_3EmissionsUpdated(address Wafer_Producer, string Country_of_Origin, uint Total_Co2_intensity);
    function updateCountry_3_Co2_Emissions (address Wafer_Producer, string memory Country_of_Origin, uint Total_Co2_intensity) external onlyDesignated_National_Authority_3{

        emit Country_3EmissionsUpdated(Wafer_Producer,  Country_of_Origin,  Total_Co2_intensity);
    }

    event Country_4EmissionsUpdated(address Chip_Designer, string Country_of_Origin, uint Total_Co2_intensity);
    function updateCountry_4_Co2_Emissions (address Chip_Designer, string memory Country_of_Origin, uint Total_Co2_intensity) external onlyDesignated_National_Authority_4{

        emit Country_4EmissionsUpdated(Chip_Designer,Country_of_Origin,Total_Co2_intensity);
    }

    event Country_5EmissionsUpdated(address Chip_Manufacturer, string Country_of_Origin, uint Total_Co2_intensity);
    function updateCountry_5_Co2_Emissions (address Chip_Manufacturer, string memory Country_of_Origin, uint Total_Co2_intensity) external onlyDesignated_National_Authority_5{

        emit Country_5EmissionsUpdated(Chip_Manufacturer,Country_of_Origin,Total_Co2_intensity);
    }

    event Country_6EmissionsUpdated(address Chip_Tester, string Country_of_Origin, uint Total_Co2_intensity);
    function updateCountry_6_Co2_Emissions (address Chip_Tester, string memory Country_of_Origin, uint Total_Co2_intensity ) external onlyDesignated_National_Authority_6{

        emit Country_6EmissionsUpdated(Chip_Tester,Country_of_Origin,Total_Co2_intensity);
    }
}

contract Indexing{

address payable Global_Regulatory_Authority;

Registration RegistrationContract;

    address Data_Processing_Oracle;
    address Time_Series_Analysis_Oracle;
    address  Emission_Index_Oracle;

    constructor(address registration) {
        RegistrationContract=Registration(registration);
        
        if(!RegistrationContract.isGlobal_Regulatory_Authority(msg.sender))
            revert("Sender not authorized");
    
        }
    modifier onlyData_Processing_Oracle{
        require(RegistrationContract.Data_Processing_OracleExists(msg.sender),
        "Sender not authorized."
        );
        _;
        } 
    
    modifier onlyTime_Series_Analysis_Oracle{
        require(RegistrationContract.Time_Series_Analysis_OracleExists(msg.sender),
        "Sender not authorized."
        );
        _;
        } 
    
     modifier onlyEmission_Index_Oracle{
        require(RegistrationContract.Emission_Index_OracleExists(msg.sender),
        "Sender not authorized."
        );
        _;
        } 
    event DataPreprocessinghashUpdated (string Preprocessed_data_hash);
    function updatePreprocessedDataHash(string memory Preprocessed_data_hash) external onlyData_Processing_Oracle {
        emit DataPreprocessinghashUpdated(Preprocessed_data_hash);
    } 

    event TimeSeriesAnalysisHashUpdated (string TimeSeriesAnalysis_hash);
    function updateTimeSeriesAnalysisHash(string memory TimeSeriesAnalysis_hash) external onlyTime_Series_Analysis_Oracle {
        emit TimeSeriesAnalysisHashUpdated(TimeSeriesAnalysis_hash);
    } 

    mapping(string => string) public countryIndex;
    string[] public countryNames;

     event CountryIndexUpdated(string countryName, string newIndex);
    function updateEmissionIndex(string[] memory _countries, string[] memory _indices) external onlyEmission_Index_Oracle {
        require(_countries.length == _indices.length, "Array lengths do not match");
        
        for (uint256 i = 0; i < _countries.length; i++) {
            string memory country = _countries[i];
            string memory index = _indices[i];

           
            bool exists = false;
            for (uint256 j = 0; j < countryNames.length; j++) {
                if (keccak256(bytes(countryNames[j])) == keccak256(bytes(country))) {
                    exists = true;
                    break;
                }
            }

           
            if (!exists) {
                countryNames.push(country);
            }

           
            countryIndex[country] = index;

            emit CountryIndexUpdated(country, index);
        }
    }

    function GetAllCountriesIndex() external view returns (string[] memory) {
        return countryNames;
    }

}
