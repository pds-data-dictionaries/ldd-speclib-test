PDS4 Spectral Library Discipline Data Dictionary User's Guide  
[Last edited](#edit-history): 2025-11-11  
  
# Introduction  
1. Purpose of this User's Guide  
    - This User's Guide provides an overview of the Spectral Library Discipline Data Dictionary. The guide details how to include the dictionary in a PDS4 label, describes the organization of the dictionary's classes and attributes, provides definitions for these classes and attributes, and lists example excerpts from labels that use them.  
2. Audience  
    - This User's Guide should be useful to data providers intending to archive Spectral Library data with PDS as well as PDS Nodes who are working with these data providers.  
  
# Overview of the Spectral Library Discipline Data Dictionary  
The Spectral Library Discipline Data Dictionary contains classes and attributes specific to the Spectral Library discipline.  
Steward: Daniel Scholes, PDS Geosciences Node, scholes@wustl.edu  
  
# Document Outline  
1. [How to Include the Spectral Library Discipline Data Dictionary in a PDS4 Label](#how-to-include-the-Spectral Library-Discipline-data-dictionary-in-a-pds4-label)  
2. [Organization of Classes and Attributes](#organization-of-classes-and-attributes)  
    1. [Class Organization](#class-organization)  
    2. [Attributes by Class](#attributes-by-class)  
3. [Definitions](#definitions)  
    1. [Classes (in alphabetical order)](#classes-in-alphabetical-order)  
    2. [Attributes (in alphabetical order)](#attributes-in-alphabetical-order)  
4. [Examples](#examples)  
5. [Edit History](#edit-history)  
  
# How to Include the Spectral Library Discipline Data Dictionary in a PDS4 Label  
The dictionary consists of a set of files with names in the form PDS4_SPECLIB_xxxx_yyyy.ext, where  
- xxxx = the PDS4 Information Model version, e.g. 1O00  
- yyyy = the Spectral Library Discipline Data Dictionary version, e.g. 1500  
  
and the file extensions are  
  
- .csv = A comma-separated value table of dictionary attributes  
- .JSON = The dictionary contents in JSON format  
- .sch = The dictionary "rules" as an XML Schematron file  
- .txt = The report generated when the dictionary was built  
- .xml = The PDS4 label that describes this set of files  
- .xsd = The dictionary contents as an XML schema file  
  
Only the schema and Schematron files are needed for validating a PDS4 label.  
  
The latest version of this dictionary may be found on the PDS web site at https://pds.nasa.gov/datastandards/dictionaries/index.shtml#speclib.  
  
The following is an example showing the use of this dictionary in a PDS4 label.  
  
```
<?xml version="1.0" encoding="UTF-8"?>
<?xml-model href="https://pds.nasa.gov/pds4/pds/v1/PDS4_PDS_1O00.sch" schematypens="http://purl.oclc.org/dsdl/schematron"?>
<?xml-model href="https://pds.nasa.gov/pds4/speclib/v1/PDS4_SPECLIB_1O00_1500.sch" schematypens="http://purl.oclc.org/dsdl/schematron"?>
<Product_Observational xmlns="http://pds.nasa.gov/pds4/pds/v1"
    xmlns:speclib="http://pds.nasa.gov/pds4/speclib/v1"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="https://pds.nasa.gov/pds4/pds/v1/PDS4_PDS_1O00.xsd
                        https://pds.nasa.gov/pds4/speclib/v1/PDS4_SPECLIB_1O00_1500.xsd">
```  
  
The following is a schematic example showing the location of every Spectral Library Discipline Data Dictionary class and attribute in a PDS4 label. Note that not all classes and attributes may be mutually compatible, and the example does not include any recursion, even if recursion is allowed.  
```
<Observation_Area>
  ...
  <Discipline_Area>
    <speclib:Spectral_Library_Product>
      <speclib:processing_description/>
      <speclib:measurement_segments/>
      <speclib:Specimen_Parameters>
        <speclib:specimen_id/>
        <speclib:specimen_name/>
        <speclib:specimen_description/>
        <speclib:source_specimen_id/>
        <speclib:specimen_min_size/>
        <speclib:specimen_min_size_reported_percentile/>
        <speclib:specimen_max_size/>
        <speclib:specimen_max_size_reported_percentile/>
        <speclib:specimen_thin_section_flag/>
        <speclib:specimen_collection_location/>
        <speclib:specimen_owner_location/>
        <speclib:specimen_owner_name/>
        <speclib:specimen_provider_name/>
      </speclib:Specimen_Parameters>
      <speclib:Specimen_Classification>
        <speclib:specimen_type/>
        <speclib:material_common_name/>
        <speclib:material_origin/>
        <speclib:synthetic_type/>
        <speclib:material_state/>
        <speclib:organic_type/>
        <speclib:material_type/>
        <speclib:material_subtype/>
        <speclib:mineral_type/>
        <speclib:mineral_subtype/>
        <speclib:rock_type/>
        <speclib:rock_subtype/>
        <speclib:volatile_type/>
        <speclib:synthetic_processing_description/>
        <speclib:specimen_ph/>
        <speclib:specimen_dilution_method/>
        <speclib:specimen_solute_standard/>
      </speclib:Specimen_Classification>
      <speclib:Measurement_Parameters>
        <speclib:segment_number/>
        <speclib:measurement_type/>
        <speclib:spectral_range_parameter_name/>
        <speclib:spectral_range_min/>
        <speclib:spectral_range_max/>
        <speclib:spectral_range_unit_name/>
        <speclib:spectral_sampling_interval_min/>
        <speclib:spectral_sampling_interval_max/>
        <speclib:spectral_sampling_interval_unit_name/>
        <speclib:spectral_resolution_width_min/>
        <speclib:spectral_resolution_width_max/>
        <speclib:spectral_resolution_width_unit_name/>
        <speclib:measurement_run/>
        <speclib:measurement_location_number/>
        <speclib:measurement_locations_per_sample/>
        <speclib:measurement_reference_standard/>
        <speclib:measurement_geometry_type/>
        <speclib:incidence_angle/>
        <speclib:emission_angle/>
        <speclib:phase_angle/>
        <speclib:measurement_source_description/>
        <speclib:measurement_atmosphere_pressure/>
        <speclib:measurement_atmosphere_temperature/>
        <speclib:measurement_atmosphere_relative_humidity/>
        <speclib:measurement_atmosphere_composition/>
        <speclib:measurement_atmosphere_description/>
        <speclib:measurement_date_time/>
        <speclib:data_producer_name/>
        <speclib:data_provider_name/>
        <speclib:measurement_requestor/>
        <speclib:measurement_notes/>
        <speclib:accumulation_time/>
        <speclib:microscope_objective/>
        <speclib:laser_pulses_per_integration/>
        <speclib:laser_attenuation/>
        <speclib:laser_power_sample/>
        <speclib:laser_power_for_calibration_min/>
        <speclib:laser_power_for_calibration_max/>
        <speclib:laser_wavelength/>
        <speclib:laser_pulse_rate/>
        <speclib:laser_averaged_integrations/>
        <speclib:dark_subtraction_flag/>
        <speclib:laser_pulses_discarded/>
        <speclib:laser_integrations_saturated/>
        <speclib:Measurement_Instrument>
          <speclib:instrument_name/>
          <speclib:Internal_Reference>
          </speclib:Internal_Reference>
        </speclib:Measurement_Instrument>
      </speclib:Measurement_Parameters>
      <speclib:Ancillary_Product>
        <speclib:ancillary_product_type/>
        <speclib:Internal_Reference>
        </speclib:Internal_Reference>
      </speclib:Ancillary_Product>
    </speclib:Spectral_Library_Product>
  </Discipline_Area>
  ...
</Observation_Area>
```  
  
The namespace for the Spectral Library Discipline Data Dictionary is http://pds.nasa.gov/pds4/speclib/v1, abbreviated "speclib:".  
  
# Organization of Classes and Attributes  
  
## Class Organization  
Below is a structured list showing the organization of classes, ordered by appearance in the PDS4 label. Each class name is linked to its complete definition in the [Definitions](#definitions) section.  
- [Spectral_Library_Product](#spectral_library_product)  
  - [Specimen_Parameters](#specimen_parameters)  
  - [Specimen_Classification](#specimen_classification)  
  - [Measurement_Parameters](#measurement_parameters)  
    - [Measurement_Instrument](#measurement_instrument)  
      - [Internal_Reference](#internal_reference)  
  - [Ancillary_Product](#ancillary_product)  
    - [Internal_Reference](#internal_reference)  
  
## Attributes by Class  
The attributes immediately under each class (if any) are listed below. Both classes and attributes are ordered by appearance in the PDS4 label; however, each class is listed only once, even if that class can appear in more than one place in a PDS4 label. Each class and attribute name is linked to its complete definition in the [Definitions](#definitions) section.  
  
### [Spectral_Library_Product](#spectral_library_product) (attribute list)  
- [processing_description](#processing_description)  
- [measurement_segments](#measurement_segments)  
  
### [Specimen_Parameters](#specimen_parameters) (attribute list)  
- [specimen_id](#specimen_id)  
- [specimen_name](#specimen_name)  
- [specimen_description](#specimen_description)  
- [source_specimen_id](#source_specimen_id)  
- [specimen_min_size](#specimen_min_size)  
- [specimen_min_size_reported_percentile](#specimen_min_size_reported_percentile)  
- [specimen_max_size](#specimen_max_size)  
- [specimen_max_size_reported_percentile](#specimen_max_size_reported_percentile)  
- [specimen_thin_section_flag](#specimen_thin_section_flag)  
- [specimen_collection_location](#specimen_collection_location)  
- [specimen_owner_location](#specimen_owner_location)  
- [specimen_owner_name](#specimen_owner_name)  
- [specimen_provider_name](#specimen_provider_name)  
  
### [Specimen_Classification](#specimen_classification) (attribute list)  
- [specimen_type](#specimen_type)  
- [material_common_name](#material_common_name)  
- [material_origin](#material_origin)  
- [synthetic_type](#synthetic_type)  
- [material_state](#material_state)  
- [organic_type](#organic_type)  
- [material_type](#material_type)  
- [material_subtype](#material_subtype)  
- [mineral_type](#mineral_type)  
- [mineral_subtype](#mineral_subtype)  
- [rock_type](#rock_type)  
- [rock_subtype](#rock_subtype)  
- [volatile_type](#volatile_type)  
- [synthetic_processing_description](#synthetic_processing_description)  
- [specimen_ph](#specimen_ph)  
- [specimen_dilution_method](#specimen_dilution_method)  
- [specimen_solute_standard](#specimen_solute_standard)  
  
### [Measurement_Parameters](#measurement_parameters) (attribute list)  
- [segment_number](#segment_number)  
- [measurement_type](#measurement_type)  
- [spectral_range_parameter_name](#spectral_range_parameter_name)  
- [spectral_range_min](#spectral_range_min)  
- [spectral_range_max](#spectral_range_max)  
- [spectral_range_unit_name](#spectral_range_unit_name)  
- [spectral_sampling_interval_min](#spectral_sampling_interval_min)  
- [spectral_sampling_interval_max](#spectral_sampling_interval_max)  
- [spectral_sampling_interval_unit_name](#spectral_sampling_interval_unit_name)  
- [spectral_resolution_width_min](#spectral_resolution_width_min)  
- [spectral_resolution_width_max](#spectral_resolution_width_max)  
- [spectral_resolution_width_unit_name](#spectral_resolution_width_unit_name)  
- [measurement_run](#measurement_run)  
- [measurement_location_number](#measurement_location_number)  
- [measurement_locations_per_sample](#measurement_locations_per_sample)  
- [measurement_reference_standard](#measurement_reference_standard)  
- [measurement_geometry_type](#measurement_geometry_type)  
- [incidence_angle](#incidence_angle)  
- [emission_angle](#emission_angle)  
- [phase_angle](#phase_angle)  
- [measurement_source_description](#measurement_source_description)  
- [measurement_atmosphere_pressure](#measurement_atmosphere_pressure)  
- [measurement_atmosphere_temperature](#measurement_atmosphere_temperature)  
- [measurement_atmosphere_relative_humidity](#measurement_atmosphere_relative_humidity)  
- [measurement_atmosphere_composition](#measurement_atmosphere_composition)  
- [measurement_atmosphere_description](#measurement_atmosphere_description)  
- [measurement_date_time](#measurement_date_time)  
- [data_producer_name](#data_producer_name)  
- [data_provider_name](#data_provider_name)  
- [measurement_requestor](#measurement_requestor)  
- [measurement_notes](#measurement_notes)  
- [accumulation_time](#accumulation_time)  
- [microscope_objective](#microscope_objective)  
- [laser_pulses_per_integration](#laser_pulses_per_integration)  
- [laser_attenuation](#laser_attenuation)  
- [laser_power_sample](#laser_power_sample)  
- [laser_power_for_calibration_min](#laser_power_for_calibration_min)  
- [laser_power_for_calibration_max](#laser_power_for_calibration_max)  
- [laser_wavelength](#laser_wavelength)  
- [laser_pulse_rate](#laser_pulse_rate)  
- [laser_averaged_integrations](#laser_averaged_integrations)  
- [dark_subtraction_flag](#dark_subtraction_flag)  
- [laser_pulses_discarded](#laser_pulses_discarded)  
- [laser_integrations_saturated](#laser_integrations_saturated)  
  
### [Measurement_Instrument](#measurement_instrument) (attribute list)  
- [instrument_name](#instrument_name)  
  
### [Internal_Reference](#internal_reference) (attribute list)  
  
### [Ancillary_Product](#ancillary_product) (attribute list)  
- [ancillary_product_type](#ancillary_product_type)  
  
# Definitions  
  
## Classes (in alphabetical order)  
  
### Ancillary_Product  
The Ancillary_Product class identifies an ancillary measurement related to a Spectral Library specimen.  
- [go to attribute list](#ancillary_product-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Internal_Reference  
The Internal_Reference class is used to cross-reference other products in PDS4-compliant registries of PDS and its recognized international partners.  
- [go to attribute list](#internal_reference-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Measurement_Instrument  
The Measurement_Instrument class contains attributes that identify the instrument that made the measurement.  
- [go to attribute list](#measurement_instrument-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Measurement_Parameters  
The Measurement_Parameters class contains attributes relevant to a single measurement of a specimen.  
- [go to attribute list](#measurement_parameters-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Specimen_Classification  
The Specimen_Classification class provides information about how a specimen has been classified.  
- [go to attribute list](#specimen_classification-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Specimen_Parameters  
The Specimen_Parameters class provides information about a specimen for which measurements have been made.  
- [go to attribute list](#specimen_parameters-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Spectral_Library_Product  
The Spectral_Library_Product class provides information about a data product in the Spectral Library.  
- [go to attribute list](#spectral_library_product-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
## Attributes (in alphabetical order)  
  
### *accumulation_time*  
The duration for which a measurement was acquired. If more than one measurement is reported, this value corresponds to the total measurement time across all measurements.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *ancillary_product_type*  
The ancillary_product_type element provides the type of data found in an ancillary product.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values:  
  - Attenuated Total Reflectance Spectroscopy  
    - Description:  IR spectroscopic technique in which placing a sample next to a high refractive index crystal causes total internal reflection resulting in an evanescent wave that samples shallow properties of the sample  
  - Chemical Composition  
    - Description: Elemental or oxide abundances for samples  
  - Differential Scanning Calorimetry  
    - Description:  Technique in which the sample is heated and temperature is monitored to evaluate exothermic and endothermic reactions that are indicative of composition  
  - Electron Microprobe Analysis  
    - Description:  Microprobe technique in which the sample is bombarded with electrons, with resultant X-ray emission spectra indicative of sample composition  
  - Image  
    - Description:  An image of the sample  
  - Modal Mineralogy  
    - Description:  Sample mineral abundances defined as weight or volume percentages  
  - Raman Spectroscopy  
    - Description:  Spectroscopic technique based on based on inelastic scattering of monochromatic light, usually from a laser source  
  - Reflectance Spectroscopy  
    - Description:  Spectroscopic technique based on measuring the spectral properties of light scattered from samples  
  - Thermogravimetric Analysis  
    - Description:  Technique in which sample mass is measured as its temperature is increased  
  - Transmission Spectroscopy  
    - Description:  Spectroscopic technique based on measuring the spectral properties of light transmitted through samples  
  - X-ray Diffraction  
    - Description:  X-rays diffracted by a sample as a function of incident angle are used to determine sample crystal structure  
  - X-ray Fluorescence  
    - Description:  Spectroscopic technique in which the sample is bombarded by high-energy X-rays or gamma rays, with fluorescent X-ray emission spectra indicative of sample composition  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *dark_subtraction_flag*  
The dark_subtraction_flag element indicates if a spectrum has been dark subtracted.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values:  
  - N  
    - Description: No, the spectrum was not dark subtracted.  
  - Y  
    - Description: Yes, the spectrum was dark subtracted.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *data_producer_name*  
The data_producer_name element provides the name of the creator of the product. For products in RELAB, the value of data_producer_name is always "RELAB".  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *data_provider_name*  
The data_provider_name element provides the full name of the person who submitted the product to the library.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *emission_angle*  
The emission_angle element provides the angle between the local vertical at the intercept point and a vector from the intercept point to the sensor.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *incidence_angle*  
The incidence_angle element provides the angle between the local vertical at the intercept point and a vector from the intercept point to the source.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *instrument_name*  
The instrument_name element provides a descriptive name of the instrument that made a spectral measurement.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 100  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *laser_attenuation*  
The laser_attenuation element is the energy of the laser pulse used for sample ablation.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *laser_averaged_integrations*  
The laser_averaged_integrations element indicates the number of laser integrations that are averaged. A value of 1 means that the integrations are not averaged.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *laser_integrations_saturated*  
The laser_integrations_saturated element lists the number of spectra with at least one peak that saturates the spectrometer.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *laser_power_for_calibration_max*  
Maximum laser power, in percent, used during calibration.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 100  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *laser_power_for_calibration_min*  
Minimum laser power, in percent, used during calibration.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 100  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *laser_power_sample*  
Laser power, in percent, utilized during sample analysis.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 100  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *laser_pulse_rate*  
The laser_pulse_rate element indicates the frequency of laser pulses. A laser_pulse_rate of 10 Hz means that the laser fires ten times per second.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *laser_pulses_discarded*  
The laser_pulses_discarded element indicates the number of laser pulses discarded.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *laser_pulses_per_integration*  
The laser_pulses_per_integration element identifies the number of laser pulses per integration. This value is 1 for single shot spectra.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *laser_wavelength*  
Laser wavelength utilized in sample analysis.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *material_common_name*  
The material_common_name element gives the specific name of the specimen material, as specifically as it is known. For example, if a specimen is pure olivine, put "Olivine". If a specimen is a mixture of kaolinite and opal, put "Kaolinite/Opal". Indicate if "Unidentified".  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 100  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *material_origin*  
The material_origin element identifies whether the specimen is natural, synthetic, or natural/doped.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values:  
  - Natural  
    - Description: The Natural value indicates that the specimen was not made in a laboratory.  
  - Natural-Doped  
    - Description: The Natural-Doped value indicates natural rock matrices that have been doped with metal oxides.  
  - Synthetic  
    - Description: The Synthetic value indicates that the specimen or some portion of a specimen was manufactured, laboratory-generated, or naturally occuring sample that has been significantly modified (e.g. heating irradiation). Grinding and stirring alone do not count as significantly modified.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *material_state*  
The material_state element identifies the physical state of the specimen.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values:  
  - Gas  
    - Description: The Gas value indicates that the specimen is in the gas state.  
  - Liquid  
    - Description: The Liquid value indicates that the specimen is in the liquid state.  
  - Solid  
    - Description: The Solid value indicates that the specimen is in the solid state.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *material_subtype*  
The material_subtype element provides an optional descriptor for additional information about the physical state of the specimen, e.g. particulate or nonparticulate.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 10  
  
### *material_type*  
The material_type element indicates the general type of the specimen.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values:  
  - Amorphous  
    - Description:  Sample without crystalline structure or long range order, e.g., glass  
  - Brine  
    - Description:  Sample that contains solute in a liquid solvent.  
  - Consolidated Mixture  
    - Description:  Sample that is cemented or otherwise aggregated into a solid mass  
  - Element  
    - Description:  Sample composed of a single element such as metallic iron  
  - Ice  
    - Description:  Solid sample composed of gas or liquid (e.g., water vapor or water) now in solid form  
  - Mineral  
    - Description:  Sample with a given composition within a defined range of compositions and that exhibits a defined crystalline structure  
  - Organic  
    - Description:  Sample composed of organic materials  
  - Rock  
    - Description:  Solid sample composed of one or more minerals  
  - Single Particle  
    - Description:  Sample composed of a single particle  
  - Unconsolidated Mixture  
    - Description:  Sample of loose or disaggregated material that is a mixture of various minerals and/or other compounds  
- Minimum Length: 1  
- Maximum Length: 30  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *measurement_atmosphere_composition*  
The measurement_atmosphere_composition element identifies any gas(es) present in measurement environment.  
- PDS4 data type: UTF8_Text_Preserved  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 1000  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *measurement_atmosphere_description*  
The measurement_atmosphere_description decribes the atmospheric conditions through which the data was taken.  
- PDS4 data type: UTF8_Text_Preserved  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 1000  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *measurement_atmosphere_pressure*  
The measurement_atmosphere_pressure element provides the atmospheric pressure of the measurement environment.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *measurement_atmosphere_relative_humidity*  
The measurement_atmosphere_relative_humidity element provides the relative humidity of the measurement environment.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 100  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *measurement_atmosphere_temperature*  
The measurement_atmosphere_temperature element provides the temperature of the measurement environment.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *measurement_date_time*  
The measurement_date_time element identifies the date and time of the observation and measurement.  
- PDS4 data type: ASCII_Date_Time_YMD  
- Valid values: N/A  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *measurement_geometry_type*  
The measurement_geometry_type element identifies the type of geometry at which a measurement is taken.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values:  
  - Biconical  
    - Description:  Measurement taken when light is sent in to the specimen at a certain direction and in a cone-like shape and received at a certain direction and in a cone-like shape.  
  - Bidirectional  
    - Description:  Measurement taken when light is sent in to the specimen at a narrow angular range and received over a narrow angular range  
  - Directional Hemispherical  
    - Description:  Measurement taken when light is sent in to the specimen at a certain direction and received in all directions (perhaps in an integrating sphere).  
  - Hemispherical Hemispherical  
    - Description:  Measurement taken when light is sent in to the specimen at all directions and received in all directions (perhaps in an integrating sphere)  
  - Unknown  
    - Description: The measurement geometry is unknown.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *measurement_location_number*  
The measurement_location_number element indicates the location number of spectra collection on the target surface.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *measurement_locations_per_sample*  
The measurement_locations_per_sample element indicates the number of measurement locations per sample.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *measurement_notes*  
The measurement_notes element contains relevant notes about how a measurement was made.  
- PDS4 data type: UTF8_Text_Preserved  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 1000  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *measurement_reference_standard*  
The measurement_reference_standard element identifies the standard object on which observations are performed in order to calibrate a measurement.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *measurement_requestor*  
The measurement_requestor element identifies the individual or laboratory who requested the measurement. The attribute may be present with a null value. A maximum of two names are permitted.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 2  
  
### *measurement_run*  
The measurement_run element identifies the run number of the measurement in a particular day.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *measurement_segments*  
The measurement_segments are the number of individual spectra that were combined to create the final merged spectrum. If the spectrum is not merged from multiple spectra, then the value of measurement_segments is 1.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *measurement_source_description*  
The measurement_source_description element identifies the source used for the measurement such as the type of lamp, heating element, laser, or radioactive source.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *measurement_type*  
The measurement_type element identifies the type of spectroscopy performed on a specimen.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values:  
  - Attenuated Total Reflectance  
    - Description: Attenuated total reflectance (ATR) is a sampling technique used in conjunction with infrared spectroscopy which enables samples to be examined directly in the solid or liquid state without further preparation.  
  - Emission  
    - Description: The Emission value indicates emission spectroscpy, which examines the wavelengths emitted by atoms or molecules during their transition from an excited state to a lower energy state.  
  - LIBS  
    - Description: LIBS (Laser-Induced Breakdown Spectroscopy) uses a highly energetic laser pulse as its excitation source to produce emission spectra.  
  - Raman  
    - Description: The Raman value indicates Raman spectroscopy, which determines information about a material by studying the Raman scattering of monochromatic light off the material.  
  - Reflectance  
    - Description: The Reflectance value indicates reflectance spectroscopy, the study of light as a function of wavelength that has been reflected or scattered from a material.  
  - Transmission  
    - Description: The Transmission value indicates transmission spectroscopy, the study of light as a function of wavelength that has been transmitted through a material.  
  - X-Ray Absorption Near-Edge Structure  
    - Description: The X-ray Absorption Near-Edge Structure value indicates XANES spectroscopy, which determines information about a material by studying the X-ray absorption spectra of electronic transitions within an atomic core.  
  - X-Ray Diffraction  
    - Description: The X-Ray Diffraction value indicates x-ray diffraction spectroscopy, which studies the diffraction patterns of x-rays scattered off a material.  
  - X-Ray Fluorescence  
    - Description: The X-Ray Fluorescence value indicates x-ray flourescence spectroscopy, which examines the emission of x-rays from a material previously bombarded with high energy x-rays or gamma rays.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *microscope_objective*  
The microscope_objective is the magnification power of the objective lens by power (e.g. 4x, 10x).  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *mineral_subtype*  
The mineral_subtype element identifies the mineral subtype of the specimen.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 10  
  
### *mineral_type*  
The mineral_type element identifies the type of mineral to which the specimen belongs.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values:  
  - Arsenate  
    - Description: The Arsenate value indicates the specimen is an arsenate.  
  - Borate  
    - Description: The Borate valeu indicates the specimen is a borate.  
  - Carbonate  
    - Description: The Carbonate value indicates the specimen is a carbonate.  
  - Chromate  
    - Description: The Chromate value indicates the specimen is a chromate.  
  - Cyclosilicate  
    - Description: The Cyclosiliate value indicates the specimen is a sorosilicate.  
  - Halide  
    - Description: The Halide value indicates the specimen is a halide.  
  - Hydroxide  
    - Description: The Hydroxide value indicates the specimen is a hydroxide.  
  - Inosilicate  
    - Description: The Inosilicate value indicates the specimen is a inosilicate.  
  - Iodate  
    - Description: The Iodate value indicates the specimen is an iodate.  
  - Native Element  
    - Description: The Native Element value indicates the specimen is a native element or an alloy.  
  - Nesosilicate  
    - Description: The Nesosiliacte value indicates the specimen is a nesosilicate.  
  - Nitrate  
    - Description: The Nitrate value indicates the specimen is a nitrate.  
  - Organic Compound  
    - Description: The Organic Compound value indicates the specimen is an organic compound.  
  - Oxide  
    - Description: The Oxide value indicates the specimen is an oxide.  
  - Phosphate  
    - Description: The Phosphate value indicates the specimen is a sulfate.  
  - Phyllosilicate  
    - Description: The Phyllosilicate value indicates the specimen is a phyllosilicate.  
  - Sorosilicate  
    - Description: The Sorosilicate value indicates the specimen is a sorosilicate.  
  - Sulfate  
    - Description: The Sulfate value indicates the specimen is a sulfate.  
  - Sulfide  
    - Description: The Sulfide value indicates the specimen is a sulfide.  
  - Tectosilicate  
    - Description: The Tectosilicate value indicates the specimen is a tectosilicate.  
  - Unclassified  
    - Description: The Unclassified value indicates that the specimen doesn't fit into any of these categories, but is still a mineral.  
  - Vanadate  
    - Description: The Vanadate value indicates that the specimen is a vanadate.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### *organic_type*  
The organic_type element identifies the organic type to which the specimen belongs.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values:  
  - Inorganic  
    - Description: The Inorganic value indicates the specimen is not an organic material.  
  - Mixture  
    - Description: The Mixture value indicates the specimen is a mixture of organic and inorganic material.  
  - Organic  
    - Description: The Organic value indicates the specimen is an organic material.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *phase_angle*  
The phase_angle element provides the angle between incidence and emission vectors.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -180  
- Maximum value: 180  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *processing_description*  
The processing_description element provides information about how measurement(s) for a particular product were made, in addition to the information given in the Measurement Parameters class. In the case of a product created by merging multiple measurements, this element describes how the merge was done.  
- PDS4 data type: UTF8_Text_Preserved  
- Valid values: N/A  
- Minimum Length: 1  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *rock_subtype*  
The rock_subtype element identifies the rock subtype of the specimen.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 10  
  
### *rock_type*  
The rock_type element identifies the type of rock the specimen is.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values:  
  - Igneous  
    - Description:  The Igneous value indicates that the specimen is volatile-poor and was formed by the cooling of magma or lava.  
  - Metamorphic  
    - Description:  The Metamorphic value indicates that the specimen was formed by metamorphic processes (e.g., increased temperature and/or pressure conditions that altered the rock composition without melting)  
  - Sedimentary  
    - Description:  The Sedimentary value indicates that the specimen was formed by sedimentary processes (e.g., lithification of unconsolidated material, direct chemical precipitation)  
  - Unknown  
    - Description:  The Unknown value indicates that there is not enough information about the specimen to assign it a rock type  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *segment_number*  
The segment_number element identifies which segment of a merged spectrum is described by a Measurement_Parameters class. The first segment is segment number 1. If the spectrum is not merged from multiple segments, then the value of segment_number is 1.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *source_specimen_id*  
The source_specimen_id element identifies the source specimen from which the observed specimen is derived.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *specimen_collection_location*  
The specimen_collection_location element provides the place where the specimen was collected.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: Yes  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *specimen_description*  
The specimen_description element provides a short description of the specimen.  
- PDS4 data type: UTF8_Text_Preserved  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 1000  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *specimen_dilution_method*  
The specimen_dilution_method element describes the method by which dilution was conducted.  
- PDS4 data type: UTF8_Text_Preserved  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 1000  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *specimen_id*  
The specimen_id element uniquely identifies the specimen.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *specimen_max_size*  
The specimen_max_size element identifies the maximum particle size of the observed specimen.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *specimen_max_size_reported_percentile*  
The percentile reported by the specimen_max_size element. For example, a specimen_max_size_reported_percentile of 90 indicates that 90 percent of the specimen has a particle size less than or equal to specimen_max_size.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 100  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *specimen_min_size*  
The specimen_min_size element identifies the minimum particle size of the observed specimen.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *specimen_min_size_reported_percentile*  
The percentile reported by the specimen_min_size element. For example, a specimen_min_size_reported_percentile of 90 indicates that 90 percent of the specimen has a particle size greater than or equal to specimen_min_size.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 100  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *specimen_name*  
The specimen_name element identifies the specimen as it is named where it is being kept.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *specimen_owner_location*  
The specimen_owner_location element provides the institution or laboratory name where the specimen resides.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: Yes  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *specimen_owner_name*  
The specimen_owner_name element identifies the individual or laboratory to whom the specimen belongs.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: Yes  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *specimen_ph*  
The specimen_ph element provides the pH of the observed specimen.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 14  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *specimen_provider_name*  
The specimen_provider_name element gives the name of the person who provided the specimen for spectral measurement.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *specimen_solute_standard*  
The specimen_solute_standard element provides the standard used for the solute.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *specimen_thin_section_flag*  
The specimen_thin_section_flag element indicates whether or not the specimen is a thin section.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - N  
    - Description: No, the specimen is not a thin section.  
  - Y  
    - Description: Yes, the specimen is a thin section.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *specimen_type*  
The specimen_type element gives one or two terms that classify the origin of the specimen.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values:  
  - Lunar Meteorite  
    - Description: The Lunar Meteorite value means the specimen is a sample from a lunar meteorite.  
  - Mars Meteorite  
    - Description: The Mars Meteorite value means the specimen is a sample from a Mars meteorite.  
  - Other Meteorite  
    - Description: The Other Meteorite value means the specimen is a sample from a meteorite that is not a lunar or Mars meteorite.  
  - Returned Asteroid Sample  
    - Description: The Returned Asteroid Sample value means the specimen is an asteroid sample returned by a mission.  
  - Returned Lunar Sample  
    - Description: The Returned Lunar Sample value means the specimen is a lunar sample returned by a mission.  
  - Synthetic Sample  
    - Description: The Synthetic Sample value means the specimen is manufactured, laboratory-generated, or a naturally occurring sample that has been significantly modified (e.g. heating, irradiation). Grinding and stirring alone do not count as significantly modified.  
  - Terrestrial Sample  
    - Description: The Terrestrial value means the specimen is a terrestrial sample.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 2  
  
### *spectral_range_max*  
The spectral_range_max element identifies the maximum value at which a given data item was sampled. For example, a spectrum that was measured in the 0.4 to 3.5 um spectral range would have a spectral_range_max value of 3.5.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *spectral_range_min*  
The spectral_range_min element identifies the minimum value at which a given data item was sampled. For example, a spectrum that was measured in the 0.4 to 3.5 um spectral range would have a spectral_range_min value of 0.4.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *spectral_range_parameter_name*  
The spectral_range_parameter_name element identifies the name of the parameter which determines the sampling interval of the measurement.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values:  
  - Angle  
    - Description: The Angle value means the spectrum is a function of angle.  
  - Energy  
    - Description: The Energy value means the spectrum is a function of energy.  
  - Frequency  
    - Description: The Frequency value means the spectrum is a function of frequency.  
  - Time  
    - Description: The Time value means the spectrum is a function of time.  
  - Wavelength  
    - Description: The Wavelength value means the spectrum is a function of wavelength.  
  - Wavenumber  
    - Description: The Wavenumber value means the spectrum is a function of wavenumber.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *spectral_range_unit_name*  
The spectral_range_unit_name element identifies the unit of measure for the values specified by spectral_range_min and spectral_range_max.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *spectral_resolution_width_max*  
The spectral_resolution_width_max element identifies the full width at half maximum (FWHM) of a spectral band in a given spectrum. If all bands are the same width, spectral_resolution_width_min and spectral_resolution_width_max will have the same value.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *spectral_resolution_width_min*  
The spectral_resolution_width_min element identifies the full width at half minimum (FWHM) of a spectral band in a given spectrum. If all bands are the same width, spectral_resolution_width_min and spectral_resolution_width_max will have the same value.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *spectral_resolution_width_unit_name*  
The spectral_resolution_width_unit_name element identifies the unit of measure for the values specified by spectral_resolution_width_min and spectral_resolution_width_max.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *spectral_sampling_interval_max*  
The spectral_sampling_interval_max element identifies the maximum distance between band centers in a given spectrum. If all band centers are equally spaced, spectral_sampling_interval_min and spectral_sampling_interval_max will have the same value.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *spectral_sampling_interval_min*  
The spectral_sampling_interval_min element identifies the minimum distance between band centers in a given spectrum. If all band centers are equally spaced, spectral_sampling_interval_min and spectral_sampling_interval_max will have the same value.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *spectral_sampling_interval_unit_name*  
The spectral_sampling_interval_unit_name element identifies the unit of measure for the values specified by spectral_sampling_interval_min and spectral_sampling_interval_max.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *synthetic_processing_description*  
The synthetic_processing_description element describes how a synthetic specimen has been processed.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *synthetic_type*  
The synthetic_type element identifies the process by which the specimen was produced synthetically.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values:  
  - Entirely Synthetic  
    - Description: Sample that is entirely human-made  
  - From Natural  
    - Description:  A natural product chemically or mineralogically altered by a laboratory treatment (e.g., heating). Does not include size and magnetic separates of natural samples or washing by water.  
  - Hardware  
    - Description:  Portions of an instrument, e.g., portions of a spectrometer that contribute to a spectroscopic signature and thus need to be characterized  
  - Natural and Synthetic  
    - Description:  Sample that is a mixture of human-made and naturally occurring components  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *volatile_type*  
The volatile_type element indicates whether the material was volatile-poor (less than 2.0% loss on ignition) or volatile-rich (greater than 2.0% loss on ignition).  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values:  
  - Poor  
    - Description: The Poor value indicates the specimen had less than 2.0% loss on ignition.  
  - Rich  
    - Description: The Rich value indicates the specimen had greater than 2.0% loss on ignition.  
  - Unknown  
    - Description: The Unknown value indicates the specimen's volatile type is unknown.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
# Examples  
  
Example PDS4 label snippet from urn:nasa:pds:relab:data_reflectance:c0at03::1.1:  
```
<Discipline_Area>
  <speclib:Spectral_Library_Product>
    <speclib:Specimen_Parameters>
      <speclib:specimen_id>AT-TXH-003</speclib:specimen_id>
      <speclib:specimen_name>Antigorite</speclib:specimen_name>
      <speclib:specimen_min_size unit="micrometer">0</speclib:specimen_min_size>
      <speclib:specimen_max_size unit="micrometer">125</speclib:specimen_max_size>
      <speclib:specimen_collection_location xsi:nil="true" nilReason="unknown"/>
      <speclib:specimen_owner_location>Brown University, Dept. Earth, Environmental and Planetary Sciences</speclib:specimen_owner_location>
      <speclib:specimen_owner_name>Takahiro Hiroi</speclib:specimen_owner_name>
    </speclib:Specimen_Parameters>
    <speclib:Specimen_Classification>
      <speclib:specimen_type>Terrestrial Sample</speclib:specimen_type>
      <speclib:material_origin>Natural</speclib:material_origin>
      <speclib:material_state>Solid</speclib:material_state>
      <speclib:organic_type>Inorganic</speclib:organic_type>
      <speclib:material_type>Mineral</speclib:material_type>
      <speclib:material_subtype>Particulate</speclib:material_subtype>
      <speclib:mineral_type>Phyllosilicate</speclib:mineral_type>
      <speclib:mineral_subtype>Antigorite</speclib:mineral_subtype>
    </speclib:Specimen_Classification>
    <speclib:measurement_segments>1</speclib:measurement_segments>
    <speclib:Measurement_Parameters>
      <speclib:segment_number>1</speclib:segment_number>
      <speclib:Measurement_Instrument>
        <speclib:instrument_name>RELAB Bidirectional Spectrometer</speclib:instrument_name>
        <Internal_Reference>
          <lid_reference>urn:nasa:pds:context:instrument:relab.bd-vnir</lid_reference>
          <reference_type>is_instrument</reference_type>
        </Internal_Reference>
      </speclib:Measurement_Instrument>
      <speclib:measurement_type>Reflectance</speclib:measurement_type>
      <speclib:spectral_range_parameter_name>Wavelength</speclib:spectral_range_parameter_name>
      <speclib:spectral_range_min>500</speclib:spectral_range_min>
      <speclib:spectral_range_max>1000</speclib:spectral_range_max>
      <speclib:spectral_range_unit_name>nm</speclib:spectral_range_unit_name>
      <speclib:measurement_geometry_type>Bidirectional</speclib:measurement_geometry_type>
      <speclib:incidence_angle unit="deg">15</speclib:incidence_angle>
      <speclib:emission_angle unit="deg">0</speclib:emission_angle>
      <speclib:phase_angle unit="deg">15</speclib:phase_angle>
      <speclib:measurement_atmosphere_relative_humidity xsi:nil="true" nilReason="unknown"/>
      <speclib:measurement_atmosphere_description>Ambient</speclib:measurement_atmosphere_description>
      <speclib:measurement_date_time>1994-12-25</speclib:measurement_date_time>
      <speclib:data_producer_name>RELAB</speclib:data_producer_name>
      <speclib:data_provider_name>RELAB</speclib:data_provider_name>
      <speclib:measurement_requestor>Takahiro Hiroi</speclib:measurement_requestor>
    </speclib:Measurement_Parameters>
  </speclib:Spectral_Library_Product>
</Discipline_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:relab:data_reflectance:c0mb56::1.1:  
```
<Discipline_Area>
  <speclib:Spectral_Library_Product>
    <speclib:Specimen_Parameters>
      <speclib:specimen_id>MB-TXH-056</speclib:specimen_id>
      <speclib:specimen_name>Murray</speclib:specimen_name>
      <speclib:specimen_description>Carbonaceous Chondrite, CM2 , M. Zolensky sample</speclib:specimen_description>
      <speclib:specimen_min_size unit="micrometer">0</speclib:specimen_min_size>
      <speclib:specimen_max_size unit="micrometer">100</speclib:specimen_max_size>
      <speclib:specimen_collection_location>Murray Co. , Kentucky</speclib:specimen_collection_location>
      <speclib:specimen_owner_location>Brown University, Dept. Earth, Environmental and Planetary Sciences</speclib:specimen_owner_location>
      <speclib:specimen_owner_name>Takahiro Hiroi</speclib:specimen_owner_name>
    </speclib:Specimen_Parameters>
    <speclib:Specimen_Classification>
      <speclib:specimen_type>Other Meteorite</speclib:specimen_type>
      <speclib:material_origin>Natural</speclib:material_origin>
      <speclib:material_state>Solid</speclib:material_state>
      <speclib:organic_type>Inorganic</speclib:organic_type>
      <speclib:material_type>Rock</speclib:material_type>
      <speclib:material_subtype>Particulate</speclib:material_subtype>
      <speclib:rock_type>Sedimentary</speclib:rock_type>
      <speclib:rock_subtype>Carbonaceous Chondrite</speclib:rock_subtype>
      <speclib:rock_subtype>CM2</speclib:rock_subtype>
    </speclib:Specimen_Classification>
    <speclib:measurement_segments>1</speclib:measurement_segments>
    <speclib:Measurement_Parameters>
      <speclib:segment_number>1</speclib:segment_number>
      <speclib:Measurement_Instrument>
        <speclib:instrument_name>RELAB Bidirectional Spectrometer</speclib:instrument_name>
        <Internal_Reference>
          <lid_reference>urn:nasa:pds:context:instrument:relab.bd-vnir</lid_reference>
          <reference_type>is_instrument</reference_type>
        </Internal_Reference>
      </speclib:Measurement_Instrument>
      <speclib:measurement_type>Reflectance</speclib:measurement_type>
      <speclib:spectral_range_parameter_name>Wavelength</speclib:spectral_range_parameter_name>
      <speclib:spectral_range_min>500</speclib:spectral_range_min>
      <speclib:spectral_range_max>1420</speclib:spectral_range_max>
      <speclib:spectral_range_unit_name>nm</speclib:spectral_range_unit_name>
      <speclib:measurement_geometry_type>Bidirectional</speclib:measurement_geometry_type>
      <speclib:incidence_angle unit="deg">10</speclib:incidence_angle>
      <speclib:emission_angle unit="deg">0</speclib:emission_angle>
      <speclib:phase_angle unit="deg">10</speclib:phase_angle>
      <speclib:measurement_atmosphere_relative_humidity xsi:nil="true" nilReason="unknown"/>
      <speclib:measurement_atmosphere_description>Ambient</speclib:measurement_atmosphere_description>
      <speclib:measurement_date_time>1994-12-09</speclib:measurement_date_time>
      <speclib:data_producer_name>RELAB</speclib:data_producer_name>
      <speclib:data_provider_name>RELAB</speclib:data_provider_name>
      <speclib:measurement_requestor>Takahiro Hiroi</speclib:measurement_requestor>
    </speclib:Measurement_Parameters>
  </speclib:Spectral_Library_Product>
</Discipline_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:relab:data_reflectance:c3rs48::1.1:  
```
<Discipline_Area>
  <speclib:Spectral_Library_Product>
    <speclib:Specimen_Parameters>
      <speclib:specimen_id>RS-CMP-048</speclib:specimen_id>
      <speclib:specimen_name>Gorlovka slab</speclib:specimen_name>
      <speclib:specimen_description>Ordinary Chondrite, H3-4, Sample #15179   USSR-AS, Fall-Black</speclib:specimen_description>
      <speclib:specimen_collection_location>Ukraine, USSR</speclib:specimen_collection_location>
      <speclib:specimen_owner_location>Brown University, Dept. Earth, Environmental and Planetary Sciences</speclib:specimen_owner_location>
      <speclib:specimen_owner_name>Carle M. Pieters</speclib:specimen_owner_name>
    </speclib:Specimen_Parameters>
    <speclib:Specimen_Classification>
      <speclib:specimen_type>Other Meteorite</speclib:specimen_type>
      <speclib:material_origin>Natural</speclib:material_origin>
      <speclib:material_state>Solid</speclib:material_state>
      <speclib:organic_type>Inorganic</speclib:organic_type>
      <speclib:material_type>Rock</speclib:material_type>
      <speclib:material_subtype>Nonparticulate</speclib:material_subtype>
      <speclib:material_subtype>Slab</speclib:material_subtype>
      <speclib:rock_type>Sedimentary</speclib:rock_type>
      <speclib:rock_subtype>Ordinary Chondrite</speclib:rock_subtype>
    </speclib:Specimen_Classification>
    <speclib:measurement_segments>1</speclib:measurement_segments>
    <speclib:Measurement_Parameters>
      <speclib:segment_number>1</speclib:segment_number>
      <speclib:Measurement_Instrument>
        <speclib:instrument_name>RELAB Bidirectional Spectrometer</speclib:instrument_name>
        <Internal_Reference>
          <lid_reference>urn:nasa:pds:context:instrument:relab.bd-vnir</lid_reference>
          <reference_type>is_instrument</reference_type>
        </Internal_Reference>
      </speclib:Measurement_Instrument>
      <speclib:measurement_type>Reflectance</speclib:measurement_type>
      <speclib:spectral_range_parameter_name>Wavelength</speclib:spectral_range_parameter_name>
      <speclib:spectral_range_min>310</speclib:spectral_range_min>
      <speclib:spectral_range_max>2600</speclib:spectral_range_max>
      <speclib:spectral_range_unit_name>nm</speclib:spectral_range_unit_name>
      <speclib:measurement_geometry_type>Bidirectional</speclib:measurement_geometry_type>
      <speclib:incidence_angle unit="deg">30</speclib:incidence_angle>
      <speclib:emission_angle unit="deg">0</speclib:emission_angle>
      <speclib:phase_angle unit="deg">30</speclib:phase_angle>
      <speclib:measurement_atmosphere_relative_humidity xsi:nil="true" nilReason="unknown"/>
      <speclib:measurement_atmosphere_description>Ambient</speclib:measurement_atmosphere_description>
      <speclib:measurement_date_time>1988-07-13</speclib:measurement_date_time>
      <speclib:data_producer_name>RELAB</speclib:data_producer_name>
      <speclib:data_provider_name>RELAB</speclib:data_provider_name>
      <speclib:measurement_requestor>Carle M. Pieters</speclib:measurement_requestor>
    </speclib:Measurement_Parameters>
    <speclib:Ancillary_Product>
      <Internal_Reference>
        <lid_reference>urn:nasa:pds:relab:data_ancillary_chemistry:rs-cmp-048_specimenchemistry</lid_reference>
        <reference_type>data_to_ancillary_data</reference_type>
      </Internal_Reference>
      <speclib:ancillary_product_type>Chemical Composition</speclib:ancillary_product_type>
    </speclib:Ancillary_Product>
  </speclib:Spectral_Library_Product>
</Discipline_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:relab:data_reflectance:c4ls05::1.1:  
```
<Discipline_Area>
  <speclib:Spectral_Library_Product>
    <speclib:Specimen_Parameters>
      <speclib:specimen_id>LS-CMP-005-C</speclib:specimen_id>
      <speclib:specimen_name>72415,64 olivine separate &lt;45 um</speclib:specimen_name>
      <speclib:specimen_description>Silicate (Neso) , Dunite Olivine, Clear crystal separate from bulk olivine sample</speclib:specimen_description>
      <speclib:source_specimen_id>LS-CMP-005</speclib:source_specimen_id>
      <speclib:specimen_min_size unit="micrometer">0</speclib:specimen_min_size>
      <speclib:specimen_max_size unit="micrometer">45</speclib:specimen_max_size>
      <speclib:specimen_collection_location>Apollo 17</speclib:specimen_collection_location>
      <speclib:specimen_owner_location>Brown University, Dept. Earth, Environmental and Planetary Sciences</speclib:specimen_owner_location>
      <speclib:specimen_owner_name>Carle M. Pieters</speclib:specimen_owner_name>
    </speclib:Specimen_Parameters>
    <speclib:Specimen_Classification>
      <speclib:specimen_type>Returned Lunar Sample</speclib:specimen_type>
      <speclib:material_origin>Natural</speclib:material_origin>
      <speclib:material_state>Solid</speclib:material_state>
      <speclib:organic_type>Inorganic</speclib:organic_type>
      <speclib:material_type>Mineral</speclib:material_type>
      <speclib:material_subtype>Particulate</speclib:material_subtype>
      <speclib:material_subtype>Particulate Ground Sorted</speclib:material_subtype>
      <speclib:mineral_type>Nesosilicate</speclib:mineral_type>
      <speclib:mineral_subtype>Olivine</speclib:mineral_subtype>
    </speclib:Specimen_Classification>
    <speclib:measurement_segments>1</speclib:measurement_segments>
    <speclib:Measurement_Parameters>
      <speclib:segment_number>1</speclib:segment_number>
      <speclib:Measurement_Instrument>
        <speclib:instrument_name>RELAB Bidirectional Spectrometer</speclib:instrument_name>
        <Internal_Reference>
          <lid_reference>urn:nasa:pds:context:instrument:relab.bd-vnir</lid_reference>
          <reference_type>is_instrument</reference_type>
        </Internal_Reference>
      </speclib:Measurement_Instrument>
      <speclib:measurement_type>Reflectance</speclib:measurement_type>
      <speclib:spectral_range_parameter_name>Wavelength</speclib:spectral_range_parameter_name>
      <speclib:spectral_range_min>300</speclib:spectral_range_min>
      <speclib:spectral_range_max>2600</speclib:spectral_range_max>
      <speclib:spectral_range_unit_name>nm</speclib:spectral_range_unit_name>
      <speclib:measurement_geometry_type>Bidirectional</speclib:measurement_geometry_type>
      <speclib:incidence_angle unit="deg">30</speclib:incidence_angle>
      <speclib:emission_angle unit="deg">0</speclib:emission_angle>
      <speclib:phase_angle unit="deg">30</speclib:phase_angle>
      <speclib:measurement_atmosphere_relative_humidity xsi:nil="true" nilReason="unknown"/>
      <speclib:measurement_atmosphere_description>Ambient</speclib:measurement_atmosphere_description>
      <speclib:measurement_date_time>1989-12-19</speclib:measurement_date_time>
      <speclib:data_producer_name>RELAB</speclib:data_producer_name>
      <speclib:data_provider_name>RELAB</speclib:data_provider_name>
      <speclib:measurement_requestor>Carle M. Pieters</speclib:measurement_requestor>
    </speclib:Measurement_Parameters>
  </speclib:Spectral_Library_Product>
</Discipline_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:relab:data_reflectance:s1gt34::1.1:  
```
<Discipline_Area>
  <speclib:Spectral_Library_Product>
    <speclib:Specimen_Parameters>
      <speclib:specimen_id>GT-CMP-034</speclib:specimen_id>
      <speclib:specimen_name>T2 Glass 250</speclib:specimen_name>
      <speclib:specimen_description>40 % T0 60% T4</speclib:specimen_description>
      <speclib:specimen_min_size unit="micrometer">125</speclib:specimen_min_size>
      <speclib:specimen_max_size unit="micrometer">250</speclib:specimen_max_size>
      <speclib:specimen_collection_location>JSC</speclib:specimen_collection_location>
      <speclib:specimen_owner_location>Brown University, Dept. Earth, Environmental and Planetary Sciences</speclib:specimen_owner_location>
      <speclib:specimen_owner_name>Carle M. Pieters</speclib:specimen_owner_name>
    </speclib:Specimen_Parameters>
    <speclib:Specimen_Classification>
      <speclib:specimen_type>Synthetic Sample</speclib:specimen_type>
      <speclib:material_origin>Synthetic</speclib:material_origin>
      <speclib:synthetic_type>Entirely Synthetic</speclib:synthetic_type>
      <speclib:material_state>Solid</speclib:material_state>
      <speclib:organic_type>Inorganic</speclib:organic_type>
      <speclib:material_type>Amorphous</speclib:material_type>
      <speclib:material_subtype>Particulate</speclib:material_subtype>
    </speclib:Specimen_Classification>
    <speclib:measurement_segments>1</speclib:measurement_segments>
    <speclib:Measurement_Parameters>
      <speclib:segment_number>1</speclib:segment_number>
      <speclib:Measurement_Instrument>
        <speclib:instrument_name>RELAB Bidirectional Spectrometer</speclib:instrument_name>
        <Internal_Reference>
          <lid_reference>urn:nasa:pds:context:instrument:relab.bd-vnir</lid_reference>
          <reference_type>is_instrument</reference_type>
        </Internal_Reference>
      </speclib:Measurement_Instrument>
      <speclib:measurement_type>Reflectance</speclib:measurement_type>
      <speclib:spectral_range_parameter_name>Wavelength</speclib:spectral_range_parameter_name>
      <speclib:spectral_range_min>600</speclib:spectral_range_min>
      <speclib:spectral_range_max>2600</speclib:spectral_range_max>
      <speclib:spectral_range_unit_name>nm</speclib:spectral_range_unit_name>
      <speclib:measurement_geometry_type>Bidirectional</speclib:measurement_geometry_type>
      <speclib:incidence_angle unit="deg">30</speclib:incidence_angle>
      <speclib:emission_angle unit="deg">0</speclib:emission_angle>
      <speclib:phase_angle unit="deg">30</speclib:phase_angle>
      <speclib:measurement_atmosphere_relative_humidity xsi:nil="true" nilReason="unknown"/>
      <speclib:measurement_atmosphere_description>Ambient</speclib:measurement_atmosphere_description>
      <speclib:measurement_date_time>1985-08-12</speclib:measurement_date_time>
      <speclib:data_producer_name>RELAB</speclib:data_producer_name>
      <speclib:data_provider_name>RELAB</speclib:data_provider_name>
      <speclib:measurement_requestor>Carle M. Pieters</speclib:measurement_requestor>
    </speclib:Measurement_Parameters>
  </speclib:Spectral_Library_Product>
</Discipline_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:relab:data_reflectance:kopx22n::1.0:  
```
<Discipline_Area>
  <speclib:Spectral_Library_Product>
    <speclib:Specimen_Parameters>
      <speclib:specimen_id>PX-ECS-022-N</speclib:specimen_id>
      <speclib:specimen_name>Hershell diopside 38-63 um wet-sieved</speclib:specimen_name>
      <speclib:specimen_min_size unit="micrometer">38</speclib:specimen_min_size>
      <speclib:specimen_max_size unit="micrometer">63</speclib:specimen_max_size>
      <speclib:specimen_collection_location>Hershel, Ontario</speclib:specimen_collection_location>
      <speclib:specimen_owner_location>Mount Holyoke College</speclib:specimen_owner_location>
      <speclib:specimen_owner_name>Elizabeth C. Sklute</speclib:specimen_owner_name>
    </speclib:Specimen_Parameters>
    <speclib:Specimen_Classification>
      <speclib:specimen_type>Terrestrial Sample</speclib:specimen_type>
      <speclib:material_origin>Natural</speclib:material_origin>
      <speclib:material_state>Solid</speclib:material_state>
      <speclib:organic_type>Inorganic</speclib:organic_type>
      <speclib:material_type>Mineral</speclib:material_type>
      <speclib:material_subtype>Particulate</speclib:material_subtype>
      <speclib:mineral_type>Inosilicate</speclib:mineral_type>
      <speclib:mineral_subtype>Pyroxene Clinopyroxene Diopside</speclib:mineral_subtype>
    </speclib:Specimen_Classification>
    <speclib:measurement_segments>1</speclib:measurement_segments>
    <speclib:Measurement_Parameters>
      <speclib:segment_number>1</speclib:segment_number>
      <speclib:Measurement_Instrument>
        <speclib:instrument_name>RELAB Bidirectional Spectrometer</speclib:instrument_name>
        <Internal_Reference>
          <lid_reference>urn:nasa:pds:context:instrument:relab.bd-vnir</lid_reference>
          <reference_type>is_instrument</reference_type>
        </Internal_Reference>
      </speclib:Measurement_Instrument>
      <speclib:measurement_type>Reflectance</speclib:measurement_type>
      <speclib:spectral_range_parameter_name>Wavelength</speclib:spectral_range_parameter_name>
      <speclib:spectral_range_min>320</speclib:spectral_range_min>
      <speclib:spectral_range_max>2540</speclib:spectral_range_max>
      <speclib:spectral_range_unit_name>nm</speclib:spectral_range_unit_name>
      <speclib:measurement_reference_standard>Spectralon</speclib:measurement_reference_standard>
      <speclib:measurement_geometry_type>Bidirectional</speclib:measurement_geometry_type>
      <speclib:incidence_angle unit="deg">45</speclib:incidence_angle>
      <speclib:emission_angle unit="deg">-10</speclib:emission_angle>
      <speclib:phase_angle unit="deg">55</speclib:phase_angle>
      <speclib:measurement_source_description>Xenon/Halogen</speclib:measurement_source_description>
      <speclib:measurement_atmosphere_relative_humidity>35</speclib:measurement_atmosphere_relative_humidity>
      <speclib:measurement_atmosphere_description>Ambient</speclib:measurement_atmosphere_description>
      <speclib:measurement_date_time>2021-10-06</speclib:measurement_date_time>
      <speclib:data_producer_name>RELAB</speclib:data_producer_name>
      <speclib:data_provider_name>RELAB</speclib:data_provider_name>
      <speclib:measurement_requestor>Elizabeth C. Sklute</speclib:measurement_requestor>
    </speclib:Measurement_Parameters>
    <speclib:Ancillary_Product>
      <Internal_Reference>
        <lid_reference>urn:nasa:pds:relab:data_ancillary_image:px-ecs-022-n_onshallow14mmdish</lid_reference>
        <reference_type>data_to_ancillary_data</reference_type>
      </Internal_Reference>
      <speclib:ancillary_product_type>Image</speclib:ancillary_product_type>
    </speclib:Ancillary_Product>
  </speclib:Spectral_Library_Product>
</Discipline_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:xas_synthesized_glasses:data:cr_xas_h081::1.0:  
```
<Discipline_Area>
  <speclib:Spectral_Library_Product>
    <speclib:Specimen_Parameters>
      <speclib:specimen_id>H081</speclib:specimen_id>
      <speclib:specimen_name>Glass Sample H081</speclib:specimen_name>
      <speclib:specimen_description>Sample H081: SiO2 wt% = 45.9, Mg# = 51.0, Na2O+K2O = 2.5</speclib:specimen_description>
      <speclib:specimen_thin_section_flag>Y</speclib:specimen_thin_section_flag>
      <speclib:specimen_collection_location>Laboratory Sample</speclib:specimen_collection_location>
      <speclib:specimen_owner_location>The University of Tennessee, Knoxville, Department of Earth and Planetary Sciences</speclib:specimen_owner_location>
      <speclib:specimen_owner_name>Molly McCanta</speclib:specimen_owner_name>
    </speclib:Specimen_Parameters>
    <speclib:Specimen_Classification>
      <speclib:specimen_type>Synthetic Sample</speclib:specimen_type>
      <speclib:material_origin>Synthetic</speclib:material_origin>
      <speclib:synthetic_type>Entirely Synthetic</speclib:synthetic_type>
      <speclib:material_state>Solid</speclib:material_state>
      <speclib:organic_type>Inorganic</speclib:organic_type>
      <speclib:material_type>Amorphous</speclib:material_type>
      <speclib:material_subtype>Nonparticulate</speclib:material_subtype>
    </speclib:Specimen_Classification>
    <speclib:measurement_segments>1</speclib:measurement_segments>
    <speclib:Measurement_Parameters>
      <speclib:segment_number>1</speclib:segment_number>
      <speclib:Measurement_Instrument>
        <speclib:instrument_name>Beamline 13-ID-E (with Si311 Detector)</speclib:instrument_name>
        <Internal_Reference>
          <lid_reference>urn:nasa:pds:context:instrument:aps.beamline13ide</lid_reference>
          <reference_type>is_instrument</reference_type>
        </Internal_Reference>
      </speclib:Measurement_Instrument>
      <speclib:measurement_type>X-Ray Absorption Near-Edge Structure</speclib:measurement_type>
      <speclib:spectral_range_parameter_name>Energy</speclib:spectral_range_parameter_name>
      <speclib:spectral_range_min>5909</speclib:spectral_range_min>
      <speclib:spectral_range_max>6203</speclib:spectral_range_max>
      <speclib:spectral_range_unit_name>eV</speclib:spectral_range_unit_name>
      <speclib:data_producer_name>Molly McCanta</speclib:data_producer_name>
      <speclib:data_provider_name>Molly McCanta</speclib:data_provider_name>
      <speclib:accumulation_time unit="min">66</speclib:accumulation_time>
    </speclib:Measurement_Parameters>
  </speclib:Spectral_Library_Product>
</Discipline_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:frankenspectra_database:data_frankenspectra:fe-metal_aa70_frankenspectrum::1.0:  
```
<Discipline_Area>
  <speclib:Spectral_Library_Product>
    <speclib:Specimen_Parameters>
      <speclib:specimen_id>Fe-metal_AA-70</speclib:specimen_id>
      <speclib:specimen_description>Shatterboxed "dust" sample less than 10 um</speclib:specimen_description>
      <speclib:specimen_min_size unit="micrometer">0</speclib:specimen_min_size>
      <speclib:specimen_max_size unit="micrometer">5.023000</speclib:specimen_max_size>
      <speclib:specimen_max_size_reported_percentile>90</speclib:specimen_max_size_reported_percentile>
      <speclib:specimen_collection_location>Alfa Aesar 00170</speclib:specimen_collection_location>
      <speclib:specimen_owner_location>Planetary Science Institute (Tucson, AZ)</speclib:specimen_owner_location>
      <speclib:specimen_owner_name>Planetary Geosciences Lab (PSI)</speclib:specimen_owner_name>
      <speclib:specimen_provider_name>Alfa Aesar</speclib:specimen_provider_name>
    </speclib:Specimen_Parameters>
    <speclib:Specimen_Classification>
      <speclib:specimen_type>Synthetic Sample</speclib:specimen_type>
      <speclib:material_common_name>Fe-metal</speclib:material_common_name>
      <speclib:material_origin>Synthetic</speclib:material_origin>
      <speclib:synthetic_type>Entirely Synthetic</speclib:synthetic_type>
      <speclib:material_state>Solid</speclib:material_state>
      <speclib:organic_type>Inorganic</speclib:organic_type>
      <speclib:material_type>Element</speclib:material_type>
      <speclib:material_subtype>Particulate</speclib:material_subtype>
      <speclib:mineral_type>Native Element</speclib:mineral_type>
    </speclib:Specimen_Classification>
    <speclib:measurement_segments>4</speclib:measurement_segments>
    <speclib:Measurement_Parameters>
      <speclib:segment_number>1</speclib:segment_number>
      <speclib:Measurement_Instrument>
        <speclib:instrument_name>McPherson VUVAS 234/302</speclib:instrument_name>
        <Internal_Reference>
          <lid_reference>urn:nasa:pds:context:instrument:lasp.mcpherson-vuvas</lid_reference>
          <reference_type>is_instrument</reference_type>
        </Internal_Reference>
      </speclib:Measurement_Instrument>
      <speclib:measurement_type>Reflectance</speclib:measurement_type>
      <speclib:spectral_range_parameter_name>Wavelength</speclib:spectral_range_parameter_name>
      <speclib:spectral_range_min>0.120000</speclib:spectral_range_min>
      <speclib:spectral_range_max>0.250000</speclib:spectral_range_max>
      <speclib:spectral_range_unit_name>micrometers</speclib:spectral_range_unit_name>
      <speclib:measurement_reference_standard>Spectralon</speclib:measurement_reference_standard>
      <speclib:measurement_geometry_type>Biconical</speclib:measurement_geometry_type>
      <speclib:incidence_angle unit="deg">0</speclib:incidence_angle>
      <speclib:emission_angle unit="deg">30</speclib:emission_angle>
      <speclib:phase_angle unit="deg">30</speclib:phase_angle>
      <speclib:measurement_atmosphere_pressure unit="Pa">0.06666</speclib:measurement_atmosphere_pressure>
      <speclib:measurement_atmosphere_temperature unit="degC">25</speclib:measurement_atmosphere_temperature>
      <speclib:measurement_date_time>2023-04-13</speclib:measurement_date_time>
      <speclib:data_producer_name>Greg Holsclaw</speclib:data_producer_name>
      <speclib:data_provider_name>Melissa Lane</speclib:data_provider_name>
      <speclib:measurement_notes>
                Illumination type: 30 watt deuterium arc lamp (0.12-0.45 um); quartz-tungsten-halogen lamp (0.15-0.6 um) using fiber optic cable; spectral sampling of 2 nm
            </speclib:measurement_notes>
    </speclib:Measurement_Parameters>
    <speclib:Measurement_Parameters>
      <speclib:segment_number>2</speclib:segment_number>
      <speclib:Measurement_Instrument>
        <speclib:instrument_name>Ocean Optics UV-Flame</speclib:instrument_name>
        <Internal_Reference>
          <lid_reference>urn:nasa:pds:context:instrument:pgl.ocean_optics-uvflame</lid_reference>
          <reference_type>is_instrument</reference_type>
        </Internal_Reference>
      </speclib:Measurement_Instrument>
      <speclib:measurement_type>Reflectance</speclib:measurement_type>
      <speclib:spectral_range_parameter_name>Wavelength</speclib:spectral_range_parameter_name>
      <speclib:spectral_range_min>0.250221</speclib:spectral_range_min>
      <speclib:spectral_range_max>0.359638</speclib:spectral_range_max>
      <speclib:spectral_range_unit_name>micrometers</speclib:spectral_range_unit_name>
      <speclib:measurement_reference_standard>Spectralon</speclib:measurement_reference_standard>
      <speclib:measurement_geometry_type>Biconical</speclib:measurement_geometry_type>
      <speclib:incidence_angle unit="deg">0</speclib:incidence_angle>
      <speclib:emission_angle unit="deg">30</speclib:emission_angle>
      <speclib:phase_angle unit="deg">30</speclib:phase_angle>
      <speclib:measurement_atmosphere_pressure unit="Pa">95000</speclib:measurement_atmosphere_pressure>
      <speclib:measurement_atmosphere_temperature unit="degC">25</speclib:measurement_atmosphere_temperature>
      <speclib:measurement_atmosphere_relative_humidity>25</speclib:measurement_atmosphere_relative_humidity>
      <speclib:measurement_date_time>2020-11-07</speclib:measurement_date_time>
      <speclib:data_producer_name>Neil Pearson</speclib:data_producer_name>
      <speclib:data_provider_name>Melissa Lane</speclib:data_provider_name>
      <speclib:measurement_notes>
                Illumination type: deuterium arc lamp (0.2-0.5 um); quartz halogen source (0.4-0.88 um) using fiber optic cable; FWHM for instrument: 1.4 nm
            </speclib:measurement_notes>
    </speclib:Measurement_Parameters>
    <speclib:Measurement_Parameters>
      <speclib:segment_number>3</speclib:segment_number>
      <speclib:Measurement_Instrument>
        <speclib:instrument_name>Analytical Spectral Devices LabSpec 4</speclib:instrument_name>
        <Internal_Reference>
          <lid_reference>urn:nasa:pds:context:instrument:psf.asd-labspec4</lid_reference>
          <reference_type>is_instrument</reference_type>
        </Internal_Reference>
      </speclib:Measurement_Instrument>
      <speclib:measurement_type>Reflectance</speclib:measurement_type>
      <speclib:spectral_range_parameter_name>Wavelength</speclib:spectral_range_parameter_name>
      <speclib:spectral_range_min>0.360000</speclib:spectral_range_min>
      <speclib:spectral_range_max>1.800000</speclib:spectral_range_max>
      <speclib:spectral_range_unit_name>micrometers</speclib:spectral_range_unit_name>
      <speclib:measurement_reference_standard>Spectralon</speclib:measurement_reference_standard>
      <speclib:measurement_geometry_type>Biconical</speclib:measurement_geometry_type>
      <speclib:incidence_angle unit="deg">30</speclib:incidence_angle>
      <speclib:emission_angle unit="deg">0</speclib:emission_angle>
      <speclib:phase_angle unit="deg">180</speclib:phase_angle>
      <speclib:measurement_atmosphere_pressure unit="Pa">95000</speclib:measurement_atmosphere_pressure>
      <speclib:measurement_atmosphere_temperature unit="degC">25</speclib:measurement_atmosphere_temperature>
      <speclib:measurement_date_time>2019-03-14</speclib:measurement_date_time>
      <speclib:data_producer_name>Ed Cloutis</speclib:data_producer_name>
      <speclib:data_provider_name>Melissa Lane</speclib:data_provider_name>
      <speclib:measurement_notes>
                Illumination type: quartz-tungsten halogen light source; spectral sampling of 1 nm
            </speclib:measurement_notes>
    </speclib:Measurement_Parameters>
    <speclib:Measurement_Parameters>
      <speclib:segment_number>4</speclib:segment_number>
      <speclib:Measurement_Instrument>
        <speclib:instrument_name>Bruker VERTEX 80v</speclib:instrument_name>
        <Internal_Reference>
          <lid_reference>urn:nasa:pds:context:instrument:psl.bruker-vertex80v</lid_reference>
          <reference_type>is_instrument</reference_type>
        </Internal_Reference>
      </speclib:Measurement_Instrument>
      <speclib:measurement_type>Reflectance</speclib:measurement_type>
      <speclib:spectral_range_parameter_name>Wavelength</speclib:spectral_range_parameter_name>
      <speclib:spectral_range_min>1.800300</speclib:spectral_range_min>
      <speclib:spectral_range_max>20.019000</speclib:spectral_range_max>
      <speclib:spectral_range_unit_name>micrometers</speclib:spectral_range_unit_name>
      <speclib:measurement_reference_standard>Infragold</speclib:measurement_reference_standard>
      <speclib:measurement_geometry_type>Bidirectional</speclib:measurement_geometry_type>
      <speclib:incidence_angle unit="deg">0</speclib:incidence_angle>
      <speclib:emission_angle unit="deg">30</speclib:emission_angle>
      <speclib:phase_angle unit="deg">30</speclib:phase_angle>
      <speclib:measurement_atmosphere_pressure unit="Pa">700</speclib:measurement_atmosphere_pressure>
      <speclib:measurement_atmosphere_temperature unit="degC">25</speclib:measurement_atmosphere_temperature>
      <speclib:measurement_date_time>2019-07-04</speclib:measurement_date_time>
      <speclib:data_producer_name>Melissa Lane; Alessandro Maturilli</speclib:data_producer_name>
      <speclib:data_provider_name>Melissa Lane</speclib:data_provider_name>
      <speclib:measurement_notes>
                Illumination type: external, water-cooled Globar; spectral sampling of 2 cm-1
            </speclib:measurement_notes>
    </speclib:Measurement_Parameters>
  </speclib:Spectral_Library_Product>
</Discipline_Area>
```  
  
# Edit History  
*See also: [SPECLIB change log](https://github.com/pds-data-dictionaries/ldd-speclib/blob/main/CHANGELOG.md).*  
2025-11-11  Daniel Scholes
